AppleScript
macOS and OS X applications send AppleEvent messages to each other for interprocess communications (IPC). These messages can be easily scripted with AppleScript for local or remote IPC. Osascript executes AppleScript and any other Open Scripting Architecture (OSA) language scripts. A list of OSA languages installed on a system can be found by using the osalang program.AppleEvent messages can be sent independently or as part of a script. These events can locate open windows, send keystrokes, and interact with almost any open application locally or remotely.

Adversaries can use this to interact with open SSH connection, move to remote machines, and even present users with fake dialog boxes. These events cannot start applications remotely (they can start them locally though), but can interact with applications if they're already running remotely. Since this is a scripting language, it can be used to launch more common techniques as well such as a reverse shell via python [1]. Scripts can be run from the command lie via osascript /path/to/script or osascript -e "script here".

ID: T1155
Tactic: Execution, Lateral Movement
Platform:  macOS
Permissions Required:  User
Data Sources:  API monitoring, System calls, Process monitoring, Process command-line parameters
Supports Remote:  Yes
Version: 1.0
Examples
Name	Description
Dok	
Dok uses AppleScript to create a login item for persistence.[2]

Mitigation
Require that all AppleScript be signed by a trusted developer ID before being executed - this will prevent random AppleScript code from executing [3]. This subjects AppleScript code to the same scrutiny as other .app files passing through Gatekeeper.

Detection
Monitor for execution of AppleScript through osascript that may be related to other suspicious behavior occurring on the system.

References
Yerko Grbic. (2017, February 14). Macro Malware Targets Macs. Retrieved July 8, 2017.
Patrick Wardle. (n.d.). Mac Malware of 2017. Retrieved September 21, 2018.
Steven Sande. (2013, December 23). AppleScript and Automator gain new features in OS X Mavericks. Retrieved September 21, 2018.
