x---
title: Assignment 1
subtitle: Computer performance, reliability, and scalability calculation
author: Mithil Patel
---

## 1.2 
# Assumptions:
  # characters uses ASCII encoding
  # PNG image is colored


#### a. Data Sizes

| Data Item                                  | Size per Item | 
|--------------------------------------------|--------------:|
| 128 character message.                     | 128 Bytes     |
| 1024x768 PNG image                         | 2.4 MB        |
| 1024x768 RAW image                         | 1.2 MB        | 
| HD (1080p) HEVC Video (15 minutes)         | 325 MB        |
| HD (1080p) Uncompressed Video (15 minutes) | 335.25 GB     |
| 4K UHD HEVC Video (15 minutes)             | 5.25 GB       |
| 4k UHD Uncompressed Video (15 minutes)     | 1.3 TB        |
| Human Genome (Uncompressed)                | 750 MB        |
|                                            | or 200 GB     |

# Calculations
    # 128 character per message
    # 128 character * 1 byte = 128 bytes
   
## 1024x768 PNG image
    # 1024x768 = 786,432 pixels
    # 786,432 pixels * 3 bytes = 2359296 bytes = 2.4 MB
   
## 1024x768 RAW image
    # 1024x768 = 786,432 pixels
    # (786,432 pixels * 12 bits) / 8 = 1179648 bytes = 1.2 MB

## HD (1080p) HEVC Video (15 minutes)
    # Website: https://www.filecatalyst.com/blog/how-big-are-movie-files/
    # 1300 MB per hours. Therefore, 1300/4 = 325 MB for a 15 minutes video
   
## HD (1080p) Uncompressed Video (15 minutes)
    # Website: https://en.wikipedia.org/wiki/Uncompressed_video
    # For 24-bit, 1080p at 60 fps = 2.98 Gbit/s = 372.5 MB/s = 335250 MB for a 15 minute video
    # 335250 MB = 335.25 GB
   
## 4K UHD HEVC Video (15 minutes)
    # Website: https://www.filecatalyst.com/blog/how-big-are-movie-files/
    # 21 GB per hours. Therefore, 21/4 = 5.25 GB for a 15 minute video
   
## 4k UHD Uncompressed Video (15 minutes)
    # Website: https://en.wikipedia.org/wiki/Uncompressed_video
    # 24-bit, 4K UHD at 60 fps = 11.9 Gbits/s = 1.487 GB/s = 1338.75 GB for a 15 minute video
    # 1338.75 GB = 1.3388 TB
   
## Human Genome (Uncompressed)
    # Website: https://medium.com/precision-medicine/how-big-is-the-human-genome-e90caa3409b0





#### b. Scaling

|                                           | Size     |  # HD  | 
|-------------------------------------------|---------:|-------:|
| Daily Twitter Tweets (Uncompressed)       | 64 GB    | 1      |
| Daily Twitter Tweets (Snappy Compressed)  | 38.4 GB  | 1      |
| Daily Instagram Photos                    | 180 TB   | 54     |
| Daily YouTube Videos                      | 936.1 TB | 281    |
| Yearly Twitter Tweets (Uncompressed)      | 23.4 TB  | 8      |
| Yearly Twitter Tweets (Snappy Compressed) | 14 TB    | 5      |
| Yearly Instagram Photos                   | 65.7 PB  | 19,710 |
| Yearly YouTube Videos                     | 341.7 PB | 102,504|

# Calculations

## Daily Twitter Tweets (Uncompressed)
    # 500,000,000 tweet * 128 character/tweet = 64,000,000,000 character
    # 1 character = 1 bytes, then 64,000,000,000 character = 64,000,000,000 bytes = 64 GB
    # 64 GB * 3 = 192 GB >> 1 HD

## Daily Twitter Tweets (Snappy Compressed)
    # Snappy compression performance (20% to 100%), then we midpoint is 60%
    # 64 * 0.60 = 38.4 GB 
    # 38.4 * 3 = 115.2 GB >> 1 HD
   
## Daily Instagram Photos
    # 75,000,000 1024x768 PNG photos daily
    # 1 1024x768 PNG = 2.4 MB, then 180,000,000 MB, or 180 TB, for daily photos.
    # 180 * 3 = 540 TB >> 54 HD
   
## Daily YouTube Videos
    # 1080 HEVC at 30 frames for 15 minutes = 325 MB, then 21.67 MB/minute
    # 500 hours = 30000 minutes, then 21.67 * 30000 = 650.1 GB worth of video every minute on Youtube
    # 650.1 * 1440 = 936144 GB = 936.144 TB of Youtube videos daily
    # 936.144 * 3 = 2802.432 TB >> 281 HD
   
## Yearly Twitter Tweets (Uncompressed)
    # 64 GB * 365 = 23.4 TB Yearly
    # 23.4 * 3 = 70.2 TB >> 8 HD
   
## Yearly Twitter Tweets (Snappy Compressed)
    # 38.4 GB * 365 = 14 TB Yearly
    # 14 * 3 = 42 TB >> 5 HD
   
## Yearly Instagram Photos
    # 180 TB * 365 = 65.7 PB Yearly
    # 65.7 * 3 = 197.1 PB >> 19710 HD
   
## Yearly YouTube Videos
    # 936.1 TB * 365 = 341.68 PB
    # 341.68 * 3 = 1025.04 PB >> 102,504 HD
    
    
    
    
   
#### c. Reliability
|                                    | # HD    | # Failures |
|------------------------------------|--------:|-----------:|
| Twitter Tweets (Uncompressed)      | 8       |      < 1   |
| Twitter Tweets (Snappy Compressed) | 5       |      < 1   |
| Instagram Photos                   | 19,710  |      270   |
| YouTube Videos                     | 102,504 |     1404   |

# Calculation
    # According to Backblaze, the annual hard drive failure rate is 1.37%.
    # The following information can be used to our calculation.





#### d. Latency

|                           | One Way Latency      |
|---------------------------|---------------------:|
| Los Angeles to Amsterdam  | 142 ms               |
| Low Earth Orbit Satellite | 40  ms               |
| Geostationary Satellite   | 477 ms               |
| Earth to the Moon         | 1.3 s                |
| Earth to Mars             | 5-20 minutes         | 

# Calculations
   # Los Angeles to Amsterdam
    # Website: https://wondernetwork.com/pings/Amsterdam/Los%20Angeles
    
   # Low Earth Orbit Satellite
    # Website: https://www.omniaccess.com/leo/
    
   # Geostationary Satellite
    # Website: https://web.archive.org/web/20160103125227/https://www.isoc.org/inet97/proceedings/F5/F5_1.HTM
   
   # Earth to the Moon
    # Website: https://aerospaceamerica.aiaa.org/departments/exploration-telepresence/
    
   # Earth to Mars
    # Website: https://mars.nasa.gov/mars2020/spacecraft/rover/communications/