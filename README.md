# Public
All items shared publicly. Free to use in any environment.
Majority of items will be PowerShell/Azure-based.
Some customizations may be required for your specific environment(s).

# Contents
- **CyberArk_Install-Agent.ps1**  
  PowerShell script for **Windows** that authenticates to the CyberArk SaaS EPM API, finds the latest EPM agent package for the current OS architecture, downloads the MSI and configuration, and installs the agent silently. Requires valid API username/password, ApplicationID, and a reinstall/protection token.
- **CyberArk_lnstall-Agent.sh**  
  Shell script for **macOS** that installs the CyberArk EPM agent. It writes logs to `/Library/Logs/Microsoft/IntuneScripts/`, verifies that the CyberArk system extensions/profile are present, reads the installation key and config from `/tmp/epmkey.txt` and `/tmp/epm.config`, unzips `/tmp/epmagent.zip`, runs the EPM installer with the installation key, configuration file, and protection token, and then cleans up the temporary files.
- **CyberArk_Uninstall-Agent.sh**  
  Shell script for **macOS** that performs a full uninstall of the CyberArk EPM agent. It logs to `/Library/Logs/Microsoft/IntuneScripts/cyberarkagentuninstall.log`, optionally uses a protection token (if provided in `securetoken`), and calls `CyberArkEPMUninstall` with `-full` to remove the agent. Returns a success or failure exit code for use with tools like Intune.

