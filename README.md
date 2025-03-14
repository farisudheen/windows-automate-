# Windows patch auto-update 
# Check if the PSWindowsUpdate module is installed
>> $module = Get-Module -ListAvailable -Name PSWindowsUpdate
>>
>> if ($module) {
>>     Write-Host "PSWindowsUpdate is already installed."
>>     # Display the path where the module is located
>>     Write-Host "Module path: $($module.ModuleBase)"
>> } else {
>>     Write-Host "PSWindowsUpdate is not installed. Installing now..."
>>     try {
>>         # Install the module
>>         Install-Module -Name PSWindowsUpdate -Force -Scope CurrentUser
>>         Write-Host "PSWindowsUpdate has been installed successfully."
>>
>>         # Get the installed module path
>>         $module = Get-Module -ListAvailable -Name PSWindowsUpdate
>>         Write-Host "Module path: $($module.ModuleBase)"
>>     } catch {
>>         Write-Host "An error occurred while installing the module: $_"
>>     }
>> }
