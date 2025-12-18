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
5. login and sync themes
6. Add a new run/debug configurations
7. Add a local tomcat
8. HTTP port 80
9. HTTPs port 443
10. JMX port 1099
11. Save it first
12. Refresh all maven dependencies and reload
13. Add the 6 exploded war artifacts
14. In project structure -> artifacts -> ensure all the exploded war's output directories are in C:\Users\Jason\IdeaProjects\maven-project\central\target\server (where server is like centralServer, etc)
15. Inside on server.xml and context.xml, change the old tailscale urls to the new ones
16. Update the locations of the certs to C:\project\tailscale.

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
12. Once the server is registered, create two users. Right click on the server, and create user appuser and viewuser
13. Once it's registered, create a new database, call it rsm_central_local
14. go to your old database on pgadmin, and backup rsm_central_local
15. go to your new central db, and restore it. Ensure that you only do this once (restoring multiple times can cause issues)
16. Do the same thing with rsm form report, etc.

# Tailscale setup
1. Install tailscale
2. Change all references in your context.xml and tomcat.xml inside of the tomcat folder, change the old tailscale urls to the new ones.
3. Run the renew_my_cert
