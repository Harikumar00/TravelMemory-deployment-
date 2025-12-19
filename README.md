# Travel Memory

`.env` file to work with the backend after creating a database in mongodb: 

```
MONGO_URI='ENTER_YOUR_URL'
PORT=3001
```REACT_APP_BACKEND_URL=http://localhost:3001
```
- Test curl screenshot
<img width="1440" height="900" alt="curl test" src="https://github.com/user-attachments/assets/abc84e33-cff8-47dc-9c16-5ee9dffc788c" />

- front end ec2
<img width="1440" height="900" alt="Frontend ec2" src="https://github.com/user-attachments/assets/f0f7edd0-d28a-4de0-ab14-8014c33566fb" />

- backend ec2
<img width="1440" height="921" alt="backend ec2" src="https://github.com/user-attachments/assets/f5cd4959-7c9b-465b-a9b5-c37b169e965b" />

- Cloudflair DNS
  <img width="1440" height="900" alt="cloudflair dns" src="https://github.com/user-attachments/assets/58822168-01fb-4b47-9d66-7afe9f85e85b" />

- LoadBalance 
  <img width="1440" height="900" alt="Screenshot 2025-12-19 at 11 21 38" src="https://github.com/user-attachments/assets/d2616fcc-9432-4bc7-8591-45b490d1b3bf" />

- Health check
  <img width="1440" height="900" alt="Screenshot 2025-12-19 at 11 22 40" src="https://github.com/user-attachments/assets/cc42c572-e7f1-4d47-b182-7e92ad1ddfba" />

- Browser screenshots
- <img width="1440" height="900" alt="Screenshot 2025-12-19 at 11 24 02" src="https://github.com/user-attachments/assets/e7e8d3b3-0f3f-414a-8f34-aacd99663cce" />
<img width="1440" height="900" alt="Screenshot 2025-12-19 at 11 24 19" src="https://github.com/user-attachments/assets/5c45d605-b2b6-4a5a-808f-55a71c85be53" />


- Architecture Diagram

  flowchart TB
    User[👤 User / Browser]

    CF[🌐 Cloudflare DNS<br/>SSL + CDN]

    ALB_FE[⚖️ Frontend ALB<br/>HTTP/HTTPS]
    FE_EC2[🖥️ Frontend EC2<br/>Nginx + React Build]

    ALB_BE[⚖️ Backend ALB<br/>HTTPS]
    BE1[🖥️ Backend EC2 - 1<br/>Node.js + PM2]
    BE2[🖥️ Backend EC2 - 2<br/>Node.js + PM2]

    DB[(🗄️ MongoDB Atlas<br/>Cloud Database)]

    User --> CF
    CF --> ALB_FE
    ALB_FE --> FE_EC2

    FE_EC2 -->|API Calls| ALB_BE
    ALB_BE --> BE1
    ALB_BE --> BE2

    BE1 --> DB
    BE2 --> DB


  

