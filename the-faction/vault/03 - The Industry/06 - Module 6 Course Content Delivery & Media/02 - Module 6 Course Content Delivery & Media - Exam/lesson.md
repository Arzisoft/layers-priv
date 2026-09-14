---
course: "The Industry"
module: "Module 6: Course Content Delivery & Media"
lesson: "Module 6: Course Content Delivery & Media — Exam"
type: "course_quiz"
post_id: 104112399
space_id: 24251863
source: "https://the-faction.mn.co/posts/104112399"
updated: "2026-08-10T18:15:42Z"
---

# Module 6: Course Content Delivery & Media — Exam

> Exam for **Module 6: Course Content Delivery & Media** (The Industry) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A teacher tells 30 students to open Lesson 3 simultaneously. All 30 devices request the same video over the school's shared internet connection. The video buffers for everyone. What delivery strategy prevents this?

- **A.** CDN edge caching so the video is fetched once from the origin server and the remaining 29 requests are served from a nearby cache node  ✅
- **B.** Pre-downloading all lesson videos to each student device overnight so no network requests are needed during classroom instruction time
- **C.** Staggering student access with a queuing system that lets five students load the video at a time to avoid overwhelming the connection
- **D.** Compressing all video files to the lowest quality setting by default so the total bandwidth required per stream is minimized for everyone

> **Answer:** A

### Q2. Your platform serves video lessons as 1080p MP4 files. A student on a slow school Chromebook watches the video buffer every 10 seconds while a student at home on broadband has no issues. What encoding is missing?

- **A.** A manual quality selector that lets students choose between 480p, 720p, and 1080p before the video begins playing on their device
- **B.** Adaptive bitrate streaming via HLS or DASH — encode multiple quality levels so each student gets the best quality their connection handles  ✅
- **C.** A download-first option that lets students save the complete video file to their device before watching so buffering never interrupts playback
- **D.** Server-side bandwidth detection that tests each student's connection speed at login and locks their account to a fixed quality tier permanently

> **Answer:** B

### Q3. A rural school has intermittent internet that drops several times per day. Students cannot complete lessons because every disconnection resets their progress completely. What platform capability would help?

- **A.** A progress auto-save feature that stores the student's position on the server every 30 seconds so they can resume after reconnection occurs
- **B.** An SMS notification system that alerts students when the internet connection is restored so they can return to the platform immediately
- **C.** Offline-capable content — lessons cached locally via service workers or downloadable modules so students continue learning without internet  ✅
- **D.** A lightweight text-only version of all course content that loads faster and requires minimal bandwidth to display on constrained connections

> **Answer:** C

### Q4. Your course page loads all 30 lessons with thumbnails and descriptions when a student opens Module 1. The page takes 12 seconds to load. The student only needs Lesson 1 right now. What should change?

- **A.** Compress all lesson thumbnails and preview images to reduce the total page weight while still loading every lesson simultaneously at once
- **B.** Replace individual lesson cards with a compact text-only list that shows titles and due dates without thumbnails or content descriptions
- **C.** Add a loading progress bar so students see that content is loading and know to wait rather than assuming the page is broken or frozen
- **D.** Load only the current lesson initially with the next lesson preloaded — lazy-load remaining lessons as the student scrolls or navigates  ✅

> **Answer:** D

### Q5. A teacher updates a lesson video on Monday. Students who cached the course last week still see the old version. The teacher receives complaints that students are watching outdated content. What cache strategy is needed?

- **A.** Content versioning using hashed filenames or cache-busting headers so browsers automatically fetch new versions when content changes  ✅
- **B.** A platform-wide notification that alerts all students when content has been updated and instructs them to clear their browser cache
- **C.** Disable all browser caching for video content entirely so every video request always fetches the latest version from the origin server
- **D.** Set cache expiration to one hour for all media assets so students automatically receive updated content within 60 minutes of any change

> **Answer:** A

### Q6. Your video lessons have no captions. A deaf student cannot access any video content. The school's 504 coordinator contacts you about accessibility compliance requirements. What must be added?

- **A.** A text transcript document posted alongside each video that students can read as an alternative to watching the video lesson content
- **B.** Sign language interpreter video overlays that can be toggled on for students who primarily use American Sign Language as their communication language
- **C.** Closed captions on all educational video content — legally required under ADA and Section 508 for educational technology platforms used  ✅
- **D.** An AI-powered real-time captioning service that generates approximate captions during video playback using speech recognition models

> **Answer:** C

### Q7. Course images are stored as uncompressed PNGs averaging 5MB each. A course with 20 images requires 100MB to load. On school networks the course page never finishes loading. What optimization is needed?

- **A.** Limit courses to a maximum of five images per module to reduce total page weight while preserving the highest quality visual presentation
- **B.** Compress and resize images for web delivery — convert to WebP or optimized JPEG at display dimensions with lazy loading for off-screen items  ✅
- **C.** Host all course images on a separate image-specific server so image downloads do not compete with the main application for bandwidth
- **D.** Replace static images with text descriptions of visual content so bandwidth-constrained schools can access courses without image downloads

> **Answer:** B

### Q8. Your CDN has edge servers on the US East and West Coasts. A school in rural Montana consistently sees slower load times than coastal schools. What is the CDN configuration issue?

- **A.** Rural schools should expect inherently slower speeds due to their geographic distance from all major internet infrastructure backbones
- **B.** The CDN provider needs to be replaced with one that specializes in serving rural and underserved geographic areas across the interior US
- **C.** A dedicated direct connection between your origin server and the Montana school's ISP would bypass the CDN entirely for faster routing
- **D.** Add CDN edge nodes in geographic regions where your school customers cluster — interior areas between coasts need additional presence points  ✅

> **Answer:** D

### Q9. A teacher assigns a 30-minute video lesson for homework. A student watches on their phone using mobile data. The video consumes 2GB on their family's limited data plan. What delivery option would help?

- **A.** Data-saver options — let students choose lower quality streaming or download lessons on WiFi for offline viewing to limit mobile data use  ✅
- **B.** Convert all homework video lessons to audio-only podcast format that students can stream with significantly lower mobile data consumption
- **C.** Limit video lesson assignments to classroom-only viewing where students are connected to the school's WiFi network during instruction time
- **D.** Partner with mobile carriers to zero-rate your platform's video traffic so streaming does not count against students' family data plans

> **Answer:** A

### Q10. Static course documents like syllabi, rubrics, and worksheets are served from the same application server. During peak hours, document downloads slow down the entire platform. What should be separated?

- **A.** Limit document downloads to off-peak hours by disabling the download feature during the school day when platform usage is at its highest
- **B.** Convert all downloadable documents to in-browser viewable formats so students read them online instead of downloading files to their devices
- **C.** Increase the application server's bandwidth allocation to handle both application requests and document downloads during peak usage periods
- **D.** Serve static assets from a CDN or dedicated object storage so document downloads do not compete with the application server for resources  ✅

> **Answer:** D

### Q11. Your video player auto-plays the next lesson when the current one ends. A student falls asleep and the player advances through 8 lessons. Their analytics show 8 completed but they only watched 1. What should be different?

- **A.** Remove auto-play entirely and require students to manually click a play button for every individual lesson in the course sequence always
- **B.** Track completion based only on a final quiz score at the end of each lesson rather than on video playback progress percentage reached
- **C.** Require interaction before advancing — a continuation prompt or comprehension check between lessons to verify engagement before marking done  ✅
- **D.** Add a 60-second countdown timer between lessons that cancels auto-play if the student does not click a confirmation button to proceed

> **Answer:** C

### Q12. Your PDF viewer downloads the entire 50-page document before displaying anything. A teacher assigned page 3 and the student waits for all 50 pages to load first. What rendering approach is better?

- **A.** Convert all PDF documents to individual page images during upload so each page can be requested and displayed as a separate image file
- **B.** Progressive PDF rendering — display the first pages immediately while the remaining pages load in the background behind the current view  ✅
- **C.** Split multi-page PDFs into individual single-page files during the upload process so students download only the specific page they need
- **D.** Replace PDF documents with HTML-formatted content that renders natively in the browser without requiring a separate document viewer plugin

> **Answer:** B

### Q13. Interactive simulations require JavaScript libraries totaling 15MB. Every student downloads the full 15MB on their first visit even if their lesson uses only one simulation. What should change?

- **A.** Code-split simulation libraries — load only the JavaScript needed for the current lesson's activities instead of bundling all simulations  ✅
- **B.** Pre-install all simulation libraries as a browser extension that students download once and never need to re-download during future visits
- **C.** Minify and compress the JavaScript bundle to reduce the 15MB download size while still delivering all simulation libraries in one package
- **D.** Move all interactive simulations to a separate subdomain so the main platform loads quickly and simulations load independently when opened

> **Answer:** A

### Q14. Your content uses a single origin server in Virginia. California schools see 200ms latency on every new asset. CDN-cached assets load in 20ms but newly uploaded teacher content always hits the origin. What reduces first-load latency?

- **A.** Move the origin server to a central US location like Kansas City to reduce the maximum distance between the server and any school in the country
- **B.** Pre-warm the CDN — when a teacher uploads content, push it to edge nodes proactively so the first student request hits cache not the origin  ✅
- **C.** Accept that first-load latency is an inherent limitation of CDN architecture and communicate this expectation to teachers during onboarding
- **D.** Deploy origin servers in multiple US regions so that teacher uploads are stored on the nearest origin and served locally from that location

> **Answer:** B

### Q15. A student's browser cached an old quiz version. They complete it and submit answers for questions that no longer exist in the current version. The submission fails with an error. What's needed?

- **A.** Disable browser caching for all quiz and assessment content entirely so students always receive the current version from the server directly
- **B.** Add a retry button on the submission error page that lets the student resubmit their answers after the quiz content refreshes automatically
- **C.** Display the quiz version number to students before they begin so they can verify they are taking the most recent version of the assessment
- **D.** Version-check on load — the quiz verifies it is running the current version before allowing submission and auto-refreshes if outdated found  ✅

> **Answer:** D

### Q16. Your video hosting stores one copy of each video in a single data center. A data center outage takes all video lessons offline for 8 hours during a school day. What resilience was missing?

- **A.** A backup copy of all videos stored on the platform's application server that can serve video content directly during data center outages
- **B.** An automated notification system that alerts all teachers when videos are unavailable so they can switch to alternative lesson plans quickly
- **C.** Multi-region video storage with automatic failover — if one region goes down, videos are served from another region without interruption  ✅
- **D.** A local video caching appliance installed at each school that stores frequently accessed videos and continues serving them during outages

> **Answer:** C

### Q17. A teacher embeds a YouTube video in their course. After the lesson ends, YouTube's algorithm shows recommended videos with inappropriate content. Students see these recommendations in class. What should the platform address?

- **A.** Use privacy-enhanced embed modes that disable recommendations and tracking — or host educational videos directly for complete content control  ✅
- **B.** Add a disclaimer to all embedded third-party video content warning students and teachers that recommendations are outside platform control
- **C.** Block all YouTube embeds entirely and require teachers to upload video content directly to the platform's own hosting infrastructure only
- **D.** Implement a content filter that scans YouTube recommendation thumbnails in real-time and hides any flagged as potentially inappropriate

> **Answer:** A

### Q18. Your platform compresses video by reducing frame rate from 30fps to 10fps. The resulting video looks choppy and unprofessional. Teachers and students complain about visual quality. What is the better compression approach?

- **A.** Accept the choppy playback as an acceptable tradeoff for significantly reduced file sizes and bandwidth requirements across all student devices
- **B.** Offer both the original 30fps version and the compressed 10fps version and let students choose their preferred quality level before viewing
- **C.** Apply motion smoothing interpolation after compression to artificially increase the perceived frame rate back to near-original visual quality
- **D.** Reduce resolution and bitrate instead of frame rate — 720p at 30fps with efficient codec encoding looks better than 1080p at 10fps playback  ✅

> **Answer:** D

### Q19. Students upload 500MB video projects for assignments. The upload takes 20 minutes and fails at 95% with no way to resume. They must restart from the beginning. What upload capability is needed?

- **A.** Resumable uploads with progress tracking — if the connection drops, the upload continues from where it stopped instead of fully restarting  ✅
- **B.** A file compression tool that automatically reduces video file sizes before upload so the transfer completes faster and is less likely to fail
- **C.** Limit maximum upload file sizes to 50MB and require students to compress their video projects to meet the platform's size constraints first
- **D.** A dedicated upload application that students install on their devices which handles large file transfers more reliably than the browser

> **Answer:** A

### Q20. A school in a developing country has 2 Mbps shared across 100 students. Your platform requires minimum 5 Mbps per student for video content. The school cannot use your platform at all. What should be available?

- **A.** Set a published minimum bandwidth requirement and only sell to schools that meet the technical prerequisites for full platform functionality
- **B.** Offer a discounted pricing tier for low-bandwidth schools that provides access to text content only without any video or media capabilities
- **C.** Low-bandwidth alternatives — text-based content, compressed images, audio-only lessons, and downloadable materials for constrained environments  ✅
- **D.** Partner with internet service providers in developing countries to subsidize bandwidth upgrades for schools that adopt your EdTech platform

> **Answer:** C

### Q21. Your media transcoding pipeline takes 4 hours to convert a 30-minute uploaded video to streaming format. A teacher uploads Monday morning for a Monday afternoon class. Students cannot watch it in time. What is the processing bottleneck?

- **A.** Teachers should upload content at least 24 hours in advance so the transcoding pipeline has sufficient time to process before class starts
- **B.** Optimize transcoding with parallel encoding, cloud transcoding services, or serve the original file while the optimized version processes  ✅
- **C.** Skip transcoding entirely and serve the original uploaded video file directly to students in whatever format and quality it was recorded in
- **D.** Implement a priority queue that lets teachers flag urgent uploads for expedited processing ahead of non-time-sensitive content in the pipeline

> **Answer:** B

### Q22. Your caching headers set a 1-year expiration on all platform assets. When you update CSS or JavaScript, students see broken layouts because browsers serve the year-old cached files. What is the fix?

- **A.** Reduce the cache expiration from one year to one day for all platform assets so browsers check for updates at least once every 24 hours
- **B.** Add a cache-clearing instruction page that teaches students how to force-refresh their browser when they encounter broken layout issues
- **C.** Version all assets with a build number appended as a query parameter that changes with each deployment forcing browsers to re-download them
- **D.** Use content-hashed filenames like app.a3f5b2.js — the filename changes when content changes so browsers fetch new versions automatically  ✅

> **Answer:** D

### Q23. Video thumbnails are served over HTTP while the rest of the platform uses HTTPS. A student's browser blocks the HTTP thumbnails as mixed content. Thumbnail images do not display. What is the issue?

- **A.** All assets must be served over HTTPS — browsers block HTTP resources on HTTPS pages as mixed content which causes display failures across items  ✅
- **B.** Configure the browser to allow mixed content by adding a security exception for the thumbnail image domain in the platform's content policy
- **C.** Serve thumbnails as inline base64-encoded data URIs embedded directly in the HTML so they do not require a separate HTTP network request
- **D.** Move thumbnail hosting to a subdomain of the main platform domain so the browser treats them as same-origin resources and allows HTTP loading

> **Answer:** A

### Q24. Your platform loads three third-party JavaScript libraries for video playback, analytics, and chat. Total page weight reaches 8MB. Students on slow connections wait 30 seconds for pages to load. What should be evaluated?

- **A.** Minify and compress all three libraries to reduce their combined file size while still loading all of them on every page load for all users
- **B.** Load all three libraries from a faster public CDN like cdnjs instead of bundling them with your application to improve download speeds globally
- **C.** Audit and reduce third-party dependencies — evaluate necessity of each library, defer non-critical scripts, and consider lighter alternatives  ✅
- **D.** Accept the 8MB page weight as necessary for full platform functionality and set a minimum bandwidth requirement for all customer schools

> **Answer:** C

### Q25. A student bookmarks a specific lesson URL. The teacher reorganizes the course and moves lessons to different positions. The student's bookmark now leads to the wrong lesson or a 404 error. What URL structure prevents this?

- **A.** Disable direct lesson URLs entirely and require all navigation to go through the course table of contents so bookmarks are never stale
- **B.** Stable content-based URLs using unique content IDs instead of position-based paths — IDs survive reorganization while positions change  ✅
- **C.** Maintain a redirect map that routes all old position-based URLs to the new position whenever the teacher reorganizes the course structure
- **D.** Display a course-level landing page for any broken lesson URL that shows the current table of contents so students can find their content

> **Answer:** B


---
_Take it in the browser: https://the-faction.mn.co/posts/104112399_
