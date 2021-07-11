---
title: Full Stack Web Developer at Asquared IoT
date: 2021-07-07
permalink: /posts/2021/07/Full-Stack-Web-Developer-at-Asqaured-IoT/
---

I started my internship as a Full Stack Web Developer at [Asquared IoT](https://www.asquared.ai/) on the 1st of January, 2021. [Dr Anand Deshpande](https://www.linkedin.com/in/anand-m-deshpande/), the CEO of A2IoT and CSO of AlgoAnalytics was kind enough to give me a six months internship at his startup.

## Experience

The startup was based in Pune, but due to the rampant spread of COVID-19, it was not feasible for me to travel. I was a part of the AutoML team, consisting of three other members, and was given the project of building a full stack web app around a video analysis code, that implemented anomaly detection. This app was to cater the manufacturing industries to check defects or orientation anomalies in products on conveyor belts and in the field of cyber-security.

My teammates Anish and Prabhanjan were both Data Scientist, and me being a callow undergrad, knew the technologies to be implemented, but never had real-world experience when it came to building or deploying an app for production. This was both nerve-wrecking and exhilarating, but in the end, we were successful in building and deploying the app. 

## Work
On the very first day, we had a quick introduction meet and a session on how the video analysis code worked. Later we brainstormed the structure and the layout of the app, and its aesthetics. It was decided that we were to implement Flask and its offered full suite of packages. 

I first built the **frontend** using Jinja Template Engine 2.0 and Bootstrap 5. This included the landing page, login/signup page, dashboard, new project, view existing projects, log-out and many more. As much as I am tempted to show-off the screenshots, I will not be posting it here due to company policies. 

The **backend** was a video analysis code as mentioned above, that used a deep learning techique called anomaly detection. The user was to add the desired video to be trained into a folder called "Input Videos", and when the training commences, the frames woild be outputted to the "training" and "validation" folders.

Shortly after, I proceeded to work on **storing** the information. It was discussed that SQLite3 was to be implemented. The Flask-SQLAlchemy ORM ensured steady connection between Flask and the database. Three tables were created namely Users, Projects and Jobs. Users table contained fields like username, email, password, etc; while the Projects table contained project information like name, description, video upload field, etc and hyperparameters like Epochs, GPU use, etc that could be set by the users as per their convinence for training the video. I will be describing the significance of the Jobs table in the coming paragraph. 

Redis was the weapon of choice to run the heavy, time-consuming **tasks in the background**. Redis was the message broker and redis queues was used to queue jobs, thus allowing the task to run **asynchronously**. To know the current job runnning in the background, I stored the job ID of the Redis Queue register into the Jobs table. The Jobs table contained the job ID, user and project IDs served as the foriegn keys and a job-status column, which enable the user to start, stop, resume and delete the task, while deplaying the epochs completed on the UI.

When it came to the **file structuring**, I spawn directories everytime a user or a project was created. I made a 1-N mapping for Users to Projects, ie, one user directory can have multiple project directories spawned. Each project directory had its own "Input Videos" directory, for storing the input  video and training and validation frames. 

For **deployment**, I dockerised the whole app. But later it was decided that I was to deploy it on the company servers.

## Experience

I mostly had all positive experiences during my stay. Dr Anand and my teammates were extremely amiable and informative. The environment was pretty intense initially. As an intern, I was expecting to work under a experienced supervisor, but the senior architect of the team quit mid-way through the project. This was a boon in dusguise, albiet a heavy load on my shoulder. I learnt top-notch modern technologies all by myself, and can proudly say my team was able to build a production style full stack app, which is now being used by the companies clientele.

## Conclusion
My internship ended on the 30rd of June, 2021. In the end, I would like to thank Dr Anand for giving me this opportunity to work at one of his burgeoning startups. It was a once in a lifetime learning experience, from learning state of the art techologies like **Redis, Flask, Bootstrap, Jinja Template Engine**, etc to learning soft skills such as **effective communication and valuing my peers time as much as mine**. Diamonds are made under pressure. Not that I compare myself to a diamond, but this experience helped me grow, technically and personally. Being my first ever forey into the corporate world, it was nice to see my hard work being appreciated.













