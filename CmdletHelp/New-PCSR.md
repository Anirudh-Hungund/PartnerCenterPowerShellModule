# Partner Center PowerShell Module (preview) #

## New-PCSR ##

**Get support topic for the request**

    $supportTopic = Get-PCSRTopics | Where-Object name -Contains '<support topic name>' 

**New Service Requests - Sample 1**

    New-PCSR -title '<service request title>' -description '<service request description>' -severity '<Minimal | Moderate | Critical>' -supportTopicID '<support topic id guid>'

**New Service Requests - Sample 2**

    $serviceRequestContact = [ServiceRequestContact]::new()
    $serviceRequestContact.FirstName = '<first name>'
    $serviceRequestContact.LastName = '<last name>'
    $serviceRequestContact.Email = '<email>'
    $serviceRequestContact.PhoneNumber = '<phone number>'
    
    $supportTopic = Get-PCSRTopics | Where-Object name -Contains '<support topic name>'
    
    $serviceRequestNote = [ServiceRequestNote]::new()
    $serviceRequestNote.Text = '<problem detailed description>'
    
    $serviceRequest = [ServiceRequest]::new()
    $serviceRequest.Title = '<title>'
    $serviceRequest.Description = '<description>'
    $serviceRequest.Severity = '<Minimal | Moderate | Critical>'
    $serviceRequest.supportTopicID = $supportTopic.id
    $serviceRequest.PrimaryContact = $serviceRequestContact
    $serviceRequest.NewNote = $serviceRequestNote
    
    New-PCSR -serviceRequest $serviceRequest

