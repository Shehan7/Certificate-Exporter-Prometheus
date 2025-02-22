# Certificate-Exporter-Prometheus
This is a tool to export SSL certificate expiration timestamps for Prometheus in windows servers

**Note**: This tool is designed to initiate in a multi-server environments and please follow Security best practices and guidelines before initializing the tool 



_____________________Certificate Exporter______________________

This is a tool to export SSL certificate expiration timestamps for prometheus

You can just open the `CertificateExporter.msi` to run it or use the tool as a Windows Service by following the below steps.

To use the solution as a windows service, clone the repository and follow the below steps. 

01. Open an elevated cmd

02. cd into CertificateExporter folder (Copy the files into an admin's any folder)

03. Execute command;
	.\nssm.exe install

04. Fill these details;
	- Path: C:\Windows\System32\msiexec.exe
  	- Startup Directory: C:\temp\CertificateExporter         <<<--- The folder which have the msi file
    	- Arguments: /i "C:\temp\CertificateExporter\CertificateExporter.msi" /quiet   
	- Service Name: CertificateExporter

05. Click Install

06. Go to "Services" and start the CertificateExporter service

NOTE: When starting the service, it can give you an error but the service should work fine. You can
verify it by going to `http://localhost:9120/metrics`


_______________________________________________________________

To stop and delete the service from your system, use the below steps with an elevated cmd

sc query | find "SERVICE_NAME"

Step 1 – Stop the Service
`sc stop [Service name]`

where [Service name] has been obtained from the the query above

Step 2 – Delete the Service
`sc delete [service name]`

where [Service name] has been obtained from the the query above


		Developed by : Shehan Somaweera

