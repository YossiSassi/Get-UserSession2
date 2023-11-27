# Get-UserSession2
Map account sessions at the entire domain endpoints or specific hosts. Both SMB remote sessions (users connected via smb) and interactive (RDP, local, Run As), with No admin permissions needed (optional, admin needed just for interactive logon times only).

Agentless, "living off the land" script (No dependencies required, e.g. no ActiveDirectory Module needed or RSAT) for mapping user sessions AND SMB open sessions (Remotely, using NetSessionEnum API) in a 'Hacktive Directory' domain.
No special permissions required on domain endpoints (any authenticated user should be OK). requires port 445 to be open on EndPoints (uses Remote Registry w/psloggedon.exe, SysInternals/Microsoft's tool).

By default, tries to query all enabled computer accounts in the domain. Can also specify specific computer(s).

.PARAMETER ComputerName

One or more computers to query for interactive and/or SMB sessions connected to them. 
Default is empty/optional - entire domain is queried for all online hosts.


Note: 
### If you need to know whether the interactive session(s) are Active or Disconnected, please use the 'original' "Get-UserSession" script (https://github.com/YossiSassi/Get-UserSession) 
- Note that it only shows interactive sessions, not account connected via SMB shares.
