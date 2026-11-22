# SunnySide — Deployment package

This directory contains the **original uploaded Sunnyside.war**, renamed `ROOT.war` solely to make the website accessible at `/` instead of `/Sunnyside`.

## Contents
- `ROOT.war`: Compiled SunnySide webapp (JSP, Java Servlets, CSS, JS, images).
- `Dockerfile`: Apache Tomcat 10.1 / Java 17 container, configured to listen on 8080.
- `.dockerignore`: Small deploy hygiene configuration.

## Deploy on Render
1. Create a GitHub repository and upload the **three files** in this directory to the repository root (do not upload this README if you prefer).
2. In Render, create a **New Web Service**, connect the repository and select **Docker** runtime.
3. Choose a plan you are comfortable with after checking the current Render pricing. Some free services may spin down when idle.
4. Set the port to **8080** if needed; the Dockerfile sets `PORT=8080` and `EXPOSE 8080`.
5. Deploy and open the generated Render HTTPS URL. Root `/` should route to `/home` through web.xml.
6. Check `/home`, `/pets`, `/pet?id=2`, `/adopt?pet=2`, `/contact`, `/contact.jsp`, and adoption form validation/confirmation.

## Deploy on Railway
1. Upload these files to a GitHub repository.
2. Create a Railway project and deploy the repository as a service.
3. Set `PORT=8080` (if Railway hasn't detected it), generate a public domain, and verify the above routes.
4. Check Railway pricing/usage limits before proceeding.

## Notes
- No database is provisioned; this WAR stores its pet inventory as code/resources. An adoption confirmation should not be mistaken for persistent submission storage.
- Contact phone and email currently appear to be demo placeholders; verify before public launch.
- Check pet image usage permissions and give appropriate creator credits before exposing the project publicly.
- This package hasn't been tested in a running Docker/Tomcat environment here; server and browser testing are required after deployment.
