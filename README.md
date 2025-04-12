# new-leaf-v111
Repacked v111 MapleStory private server (based on Enviction/Tera-v111)

## Local Development
### References:
- https://forum.ragezone.com/threads/how-to-make-a-maplestory-v111-lithium-based-private-server.865468/
- https://github.com/Enviction/Tera-v111
- https://forum.ragezone.com/threads/v111-tera-lidium.1225952/page-2
- Knowledge of v83 private server development is helpful, but not necessary

### Prerequisites:
- Windows OS 
- Java 19
- MySQL 5.7
- IntelliJ
- MapleStory v111 source (see next point)
- https://www.dropbox.com/scl/fi/fd6u7pwuztbqxxskdx5kf/v111.rar?rlkey=y1gctgrw48qxbymgh6innfda0&st=ipkkab6o&dl=0

### Steps:
 1. Create a new directory for your private server
 2. Download this entire GitHub source code as a ZIP
 3. Extract the contents of the ZIP into your directory
 4. There should be a v111.rar file. It is a snapshot of the working state of the server, and contains the MapleStory v111 source files as well. The only things of interest will be the /MapleStory sub-folder. Extract that with the same folder structure that you see in the .rar file.
 5. Set up your MySQL server. `database.user = root`, `database.password = admin`
 6. Create a new DB schema called `lidium`. 
 7. Execute the `lidium.sql` script under `sql/aio`. It should have executed ~507 SQL statements
 8. Create a new IntelliJ project (Java 19 SDK) that points to `Lidium-v111-Updated`. Let it index.
 9. This should already have been done for you in this source code, but update the following files: 
	 a. `Lidium-v111-Updated/db` to reference the `lidium` schema name in (6)
	 b. `src/database/DatabaseConnection.java` to do the same as (10)
 10. Run `src/server/Start.java` in IntelliJ (Shift + F10). It should build without error.
 11. Run `MapleStory/MapleStory v111.1.exe` to launch the client. 
 12. Default credentials:
	 a. Username: `admin`
	 b. Password: `admin`
	 c. PIC: `111111`
