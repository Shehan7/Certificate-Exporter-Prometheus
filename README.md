# Certificate-Exporter-Prometheus
This is a tool to export SSL certificate expiration timestamps for Prometheus


###############################################################
###############################################################
_____________________Certificate Exporter______________________
###############################################################
###############################################################
This is a tool to export SSL certificate expiration timestamps for prometheus

01. Open an elevated cmd

02. cd into CertificateExporter folder (Copy the files into an admin's any folder)

03. Execute command;
	.\nssm.exe install

04. Fill these details;
	Path: C:\Windows\System32\msiexec.exe
	Startup Directory: C:\temp\CertificateExporter         <<<--- The folder which have the msi file
	Arguments: /i "C:\temp\CertificateExporter\CertificateExporter.msi" /quiet   

	Service Name: CertificateExporter

05. Click Install

06. Go to "Services" and start the CertificateExporter service

NOTE: When starting the service, it can give you an error but the service should work fine. You can
verify it by going to http://localhost:9120/metrics





###############################################################
###############################################################
		Developed by : Shehan Somaweera
###############################################################
###############################################################
