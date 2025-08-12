# work-items

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

# Databases setup
1. Login to pgadmin
2. Register a new server
3. Host name is the tailscale name
4. Port is 5432
5. maintenance database name is postgres
6. username is postgres
7. password set to
8. Once it's registered, create a new database, call it rsm_central_local
9. go to your old database on pgadmin, and backup rsm_central_local
10. go to your new central db, and restore it. Ensure that you only do this once (restoring multiple times can cause issues)
11. Do the same thing with rsm form report, etc.
