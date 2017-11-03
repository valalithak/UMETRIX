Pre-Requisites:
1.	Windows 7 or higher 
2.	.Net Framework 4.6.1 or higher
3.	IIS 7.5
4.	SQL Server
5.	Java  (Used to Decompile APK File)

Deployment Process:
1.	Download Umetrix.zip
2.	Unzip Umetrix.zip and copy it to D drive
3.	Grant Read,Write,Execute permission to “Everyone”  for  “D:\Umetrix\Web\APKDecompile” and “D:\Umetrix\Web\App_Data” folders
4.	Create Junction for decompilation requirement
D:\>mklink /j D:\U "<PathWhereUmetrixWebIsCopied>\APKDecompile"
Example:
D:\>mklink /j D:\U "D:\Umetrix\Web\APKDecompile"
NOTE: if change link path from “D:\U” and do change it in web.config file as well
  <appSettings>
    <add key="DecompilerPath" value="D:\U\" />
  </appSettings>
5.	Execute SQL script present in Umetrix\DB_Bakup\UMETRIX_DB_Script.sql to create database.
6.	Modify database connection string in web.config to connect to restored DB backup
<connectionStrings>
    <add name="DefaultConnection" connectionString="Data Source=localhost;Initial Catalog=Umetrix;User Id=sa; Password=ppm;"
      providerName="System.Data.SqlClient" />
  </connectionStrings>
7.	Open IIS and Create Website as shown in following figure


//TODO Add Images

8.	Open IE and try to browse site http://localhost:8080 
9.	Validation Case generator is present in D:\Umetrix\ ValidationCaseGenerator \ValidationCaseGenerator.exe

