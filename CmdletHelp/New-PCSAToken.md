# Partner Center PowerShell Module (preview) #

## New-PCSAToken ##

**Set a specific token for a command/function - user authentication**

    $credential = Get-Credential

    New-PCSAToken -cspappID '<native app id GUID>' -cspDomain '<csp partner domain>' -credential $credential

**Set a specific token for a command/function - app authentication**

    $clientSecret = '<key code secret>'
	$clientSecretSecure = $clientSecret | ConvertTo-SecureString -AsPlainText -Force

    New-PCSAToken -cspappID '<native app id GUID>' -cspDomain '<csp partner domain>' -cspClientSecret $clientSecretSecure

