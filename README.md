# work-items

# Chrome setup

1. Open google chrome
2. Sign into your google account
3. Click on the three dots on the right side
4. Turn on sync (ENSURE THIS IS ON YOUR OLD COMPUTER TOO)

# IntelliJ setup

1. Copy tomcat from old computer
2. Copy to new computer
3. Install intelliJ
4. Clone the github repository
5. When prompted for login or token, choose token
6. Generate token
7. Copy that token and login
8. Trust the project
9. login and sync themes
10. Zip the tomcat, jdk, and maven folder from your old location
11. <img width="911" height="265" alt="image" src="https://github.com/user-attachments/assets/2cd29ce0-223f-492d-89d4-da8012a0e86c" />
12. Upload and transfer it to your new computer
13. Put it in the new location for your project and git repo
14. Go to the Help Tab
15. Go to Manage Subscriptions
16. Activate your subscription
17.  Add a new run/debug configurations
18. Add a local tomcat
19. HTTP port 8080
20. HTTPs port 443
21. JMX port 1099
22. Save it first
23. Refresh all maven dependencies and reload
24. Add the 6 exploded war artifacts
25. <img width="484" height="264" alt="image" src="https://github.com/user-attachments/assets/9ca6d6ac-ff97-4b82-a771-0919cf4c18b4" />

26. In project structure -> artifacts -> ensure all the exploded war's output directories are in C:\Users\Jason\IdeaProjects\maven-project\central\target\server (where server is like centralServer, etc)
27. Inside on server.xml and context.xml, change the old tailscale urls to the new ones
28. Update the locations of the certs to C:\project\tailscale.

# Databases setup (courtesy of the scrum god)
1. Open google,download postgres
2. Once downloaded, go to "C:\Program Files\PostgreSQL\17\data\pg_hba.conf"
3. Replace the last line with `host    all     	all             100.64.0.0/10           scram-sha-256`
4. Login to pgadmin
6. Register a new server
7. Host name is the tailscale name
8. Port is 5432
9. maintenance database name is postgres
10. username is postgres
11. password set to
12. Once the server is registered, create two users. Right click on the server, and create user appuser and viewuser. Use the correct passwords
13. Once it's registered, create a new database, call it rsm_central_local. Owner of this is postgres
14. go to your old database on pgadmin, and backup rsm_central_local
15. go to your new central db, and restore it. Ensure that you only do this once (restoring multiple times can cause issues)
16. Do the same thing with rsm form report, etc.

# Tailscale setup
1. Install tailscale
2. Change all references in your context.xml and tomcat.xml inside of the tomcat folder, change the old tailscale urls to the new ones.
3. Run the renew_my_cert
