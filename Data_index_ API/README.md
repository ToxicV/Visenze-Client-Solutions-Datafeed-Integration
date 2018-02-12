# Visenze-Client-Solutions-Datafeed-Integration
This python script creates a scheduled job on Visenze datafeed integration through API /insert method. It does the following: 
1. Clean image urls in the datafeed (.csv) by removing space
2. Validate image urls in the datafeed (.csv) by checking response
3. Batch insert valid image urls for indexing on Visenze dashboard server 

Steps to follow before executing the script
1. Prepare product catalogue files in CSV format, including im_name and im_url (mandatory). The details for the CSV file is below:
http://developers.visenze.com/setup/#Upload-your-datafeed

2. Configure schema fields on Visenze's dashboard (Your Images -> Config) before running the script. The details can be found below: 
http://developers.visenze.com/setup/#Configure-schema-fields

3. Install ViSearch Python SDK
```bash

$ pip install visearch

```

Running the script
```bash

$ bash ~/dir/ftp_sample.sh --upload ~/dir/your_upload_folder_name --backup ~/dir/your_backup_folder_name --ftp ~/dir/your_ftp_folder_name --username XXX --password XXX --ftp_address XXX 

```

Scheduling FTP task at 10am everyday 
```bash
crontab -e
```
```bash
0 10 * * * bash ~/dir/ftp_sample.sh --upload ~/dir/your_upload_folder_name --backup ~/dir/your_backup_folder_name --ftp ~/dir/your_ftp_folder_name --username XXX --password XXX --ftp_address XXX 
```
