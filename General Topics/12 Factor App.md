# Codebase:
Track the codebase for a 12-factor app in a version control system, like Git, with the same base of code used across multiple environments.

**Personal translation:**
Use a single spot for code.  Like a repository in Github.
Apps should not share code.  -> no monorepos.

# **Dependencies:**
Declare and isolate dependencies explicitly, ensuring no implicit reliance on system-wide packages.

**Personal translation:**
Declare the dependencies somehow, like Pythons *requirements.txt* file.  Make sure there are explicit versions set.
Use Virtual Environments like pythons *VENV* and/or Docker.

# **Config:**
Store configuration that varies between deployments in the environment, keeping the codebase agnostic to its running environment.

**Personal translation:**
Don't store config crap, like a database url, port, user/password etc, in the code.  Store this stuff in Env variables.

# **Backing services:**
Treat all backing services, like databases or messaging queues, as attached resources, accessed via a URL or other locator stored in the config.

**Personal translation:**
A [deploy](https://12factor.net/codebase) of the twelve-factor app should be able to swap out a local MySQL database with one managed by a third party (such as [Amazon RDS](http://aws.amazon.com/rds/)) without any changes to the app’s code. Likewise, a local SMTP server could be swapped with a third-party SMTP service (such as Postmark) without code changes. In both cases, only the resource handle in the config needs to change.

# **Build, release, run:**
Strictly separate the stages of build, release, and run to ensure a reliable and consistent deployment process.

**Personal translation:**
Basically every build should create a new *release*, aka **docker image** and that image should have a unique release tag so you know what you're deploying.

# **Processes:** 
Make each process within a 12-factor app stateless and shares-nothing; any data that needs to persist is stored in a stateful backing service.

**Personal translation:**
Any *stateful* information stored in the app, will get super weird when theres multiple pods because they will all have their own version of that information.  (Like if you count something, or a users **session info** if users should stay logged in if they close the app or web page, since when they come back they might be connecting to a different pod).
TDLR:  All stateful information should be stored in a single backend service that the app connects to. (this service should only have 1 instance obviously).  Like a database or redis.

# **Port binding:** 
Ensure the app is self-contained and does not rely on runtime injection of a webserver into the execution environment to create a web-facing service.

**Personal translation:**

# **Concurrency:** 
Allow the app to scale out via the process model, spawning new processes in the same manner as scaling distributed systems.

**Personal translation:**
Build the app according to the **process** model above, so it doesn't have issues scaling horozontally by having something like kubernetes spawn additional pods as needed

# **Disposability:** 
Make the app's processes disposable, meaning they can start or stop at a moment's notice to facilitate fast elastic scaling, rapid deployment of code or config changes, and robustness of production deploys.

**Personal translation:**
Don't rely on complex startup scripts or shutdown scripts

# **Dev/prod parity:**
Design the twelve-factor app for continuous deployment by keeping the gap between development and production environments as small as possible.

**Personal translation:**
Make sure all tools between environments are the same and that the environments are not to excessively different.
# **Logs:** 
Treat logs as event streams, and never concern the app with routing or storage of its output stream.

**Personal translation:**
No writing to a local file.  Either just the standard STDOUT (terminal print) or a structured JSON format that can be sent to another service using some type of logs agent (like new relic ;) )
# **Admin processes:** 
Run administrative tasks as one-off processes in an identical environment as the regular long-running processes of the app.

**Personal translation:**
Admin tasks should be separate from the app.  It should be its own app, like a separate docker image.  But it should be run in an identical setup.
