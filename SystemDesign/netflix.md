# Netflix

## Requirements
- content creator should be able to upload the media
- viewers should be able to view content 
- content should be avaibale in varying screen size and internet speed
- platform should have search functionality
- subtitle should be shown overlaid video


### System Design
#### Approach 1
![Approach 1 - system design](https://github.com/himkak/my-notes/blob/master/SystemDesign/Netflix_Approach1_SystemDesign.PNG)

![Approach 1 - Flow Diagram](https://github.com/himkak/my-notes/blob/master/SystemDesign/Netflix_Approach1_FlowDiagram.PNG)


**Flie Storage Server**
- Neflix uses AWS S3 to store all the file (video) chunks

**Different components**
- Transcoder : When the file is uploaded, it is converted into videos for different resolutions, different devices, different formats etc. This can be done paralelly, so 
- AWS S3 : All the files are uploaded into S3. 
- CDN : every region has its own CDN. Its for faster streaming of video. The videos are also prsent in the region specific CDN. Our videos are streamed from taht CND. The CDNs are present with ISPs.  This is also called OpenConnect Network.

#### Approcah 2

- https://www.youtube.com/watch?v=psQzyFfsUGU

![Approach 2 - System Design](https://github.com/himkak/my-notes/blob/master/SystemDesign/NetflixSystemDesign.JPG)


# References 

- https://youtu.be/XtsZxjWzNDA
- https://www.youtube.com/watch?v=x9Hrn0oNmJM

- https://www.youtube.com/watch?v=XtsZxjWzNDA : Netflix System Design | Media Streaming Platform | System Design Interview

- http://highscalability.com/blog/2017/12/11/netflix-what-happens-when-you-press-play.html

#### YouTube

- http://highscalability.com/youtube-architecture


## How to do capacity estimation

### Eg1 : YouTube
Total no of user base = 1 billion
No of users who upload videos = 1/1000
Size of each video (approx) = 10 mins

2 hr movie = 4GB
Youtube reduces the quiality and stores = .4GB = 400 mb
1 hr = 200 mb
10 mins = 200/60 mb *10


So total space in mb= 10^9 * 1/1000 * 200/60 * 10= 10^6 * 20/6 = 10^7 * 3.5 mb = 30 TB
For 3 replicase  = 30 * 3
90 TB is for 1 resolution