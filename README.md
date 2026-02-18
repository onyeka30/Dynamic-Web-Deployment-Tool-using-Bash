Why "Hardcoding" is the Enemy of Scalable DevOps 

I’ve spent the last few sessions in my Linux lab moving from manual server configuration to building a Dynamic Web Deployment Tool using Bash.

The Knowledge Gained:

Positional Parameters ($1, $2): I refactored my scripts to accept command-line arguments. Instead of editing code for every new site, I can now deploy any artifact by passing the URL and Name as data.

Command: ./50websetup.sh 
<img width="1366" height="768" alt="Screenshot from 2026-02-18 19-42-01" src="https://github.com/user-attachments/assets/8fc38bbb-ddb9-4db7-840f-1d79c38dba97" />

<img width="1366" height="768" alt="Screenshot from 2026-02-18 19-42-13" src="https://github.com/user-attachments/assets/952d257b-c989-4438-8068-9266d29bf75e" />


Idempotent Design: I integrated a "Clean Slate" logic. The script now ensures the /var/www/html/ directory is wiped and prepared before every deployment, preventing "configuration drift" from old files.

Automated Verification: A script is only as good as its logs. I added a silent curl verification step at the end. If the script doesn't see the expected HTML tags, the deployment isn't considered "Done."

The "Real World" Debugging Moment: The most valuable part was troubleshooting a syntax error where my rm and mkdir commands collided. It was a great reminder that automation requires precision—a single missing newline can break a deployment pipeline.

Stack: CentOS Stream 9, Vagrant, VirtualBox, Bash.

<img width="1366" height="768" alt="bashdepol" src="https://github.com/user-attachments/assets/58c32b7e-a865-46e8-b10d-fc94b5ac9551" />


