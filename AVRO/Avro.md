# AVRO by Apache
Developed by Apache
Schema defined in 2 formats: avsc, avdl
avdl is easy to write and easy to use.

## What's Apache Avro?
Avro provides:

Rich data structures.
A compact, fast, binary data format.
A container file, to store persistent data.
Remote procedure call (RPC).
Simple integration with dynamic languages. Code generation is not required to read or write data files nor to use or implement RPC protocols. Code generation as an optional optimization, only worth implementing for statically typed languages.

## AVRO RPC

### Dependencies to be added

```xml
<dependency>
  <groupId>org.apache.avro</groupId>
  <artifactId>avro</artifactId>
  <version>1.8.2</version>
</dependency>
```
As well as the Avro Maven plugin (for performing code generation.
This plugin element causes the Avro Maven Plugin's compile goal to run during the "generate-sources" maven phase.

```xml
<plugin>
  <groupId>org.apache.avro</groupId>
  <artifactId>avro-maven-plugin</artifactId>
  <version>1.8.2</version>
  <executions>
    <execution>
      <phase>generate-sources</phase>
      <goals>
        <goal>schema</goal>
      </goals>
      <configuration>
        <sourceDirectory>${project.basedir}/src/main/avro/</sourceDirectory>
        <outputDirectory>${project.basedir}/src/main/java/</outputDirectory>
      </configuration>
    </execution>
  </executions>
</plugin>
<plugin>
  <groupId>org.apache.maven.plugins</groupId>
  <artifactId>maven-compiler-plugin</artifactId>
  <configuration>
    <source>1.6</source>
    <target>1.6</target>
  </configuration>
</plugin>
```

### Sample avpr file
```jaon
{"namespace": "example.proto",
 "protocol": "Mail",

 "types": [
     {"name": "Message", "type": "record",
      "fields": [
          {"name": "to",   "type": "string"},
          {"name": "from", "type": "string"},
          {"name": "body", "type": "string"}
      ]
     }
 ],

 "messages": {
     "send": {
         "request": [{"name": "message", "type": "Message"}],
         "response": "string"
     }
 }
}
```

In this file You will see:

1.the name & namespace of the protocol
2.any specialized types used in the messages, Message in this case
3.we are declaring a "send" message type which takes a Message as an argument and returns a result string


## Application
avdl file to be placed at 'src/main/avro'

### Server code

```java

	private static Server server;

	private static void startServer() throws IOException {
		server = new NettyServer(new SpecificResponder(Mail.class, new MailImpl()),
				new InetSocketAddress("127.0.0.1", 65111));
		// the server implements the Mail protocol (MailImpl)
		server.start();
	}

	public static void main(String[] args) throws IOException, AvroRemoteException {

		System.out.println("Starting server");
		// usually this would be another app, but for simplicity
		startServer();
		System.out.println("Server started");
		// server.close();
	}

```

Reference code
https://github.com/himkak/AvroRpcSampleServer

### Client Code

```java
		NettyTransceiver client = new NettyTransceiver(new InetSocketAddress("localhost",65111));
		// client code - attach to the server and send a message
		Mail proxy = (Mail) SpecificRequestor.getClient(Mail.class, client);
		
		proxy.send(message)//The method defined in the avdl file

```
Reference code
https://github.com/himkak/AvroRpcSampleClient


# References
[Getting Started AVRO]https://avro.apache.org/docs/1.8.2/gettingstartedjava.html
[AVRO RPC]https://github.com/phunt/avro-rpc-quickstart
https://iwayinfocenter.informationbuilders.com/TLs/TL_soa_ism_component/source/avro_components51.htm

[NioClientSocketChannelFactory ChannelFactory] https://github.com/rxnzero/apache-avro-example/blob/master/src/main/java/example/avro/rpc/CalculatorDynamicClient.java
