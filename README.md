# opttc
on prem to the cloud notes

# ENTER PARAMETERS WHERE *'S ARE

# CREATE RESOURCE GROUP
az group create --name * --location *

# CREATE AZURE SQL 
az  deployment group create --resource-group opttc  --parameters "{ \"location\": { \"value\": \"*\" } }" "{ \"serverName\": { \"value\": \"*\" } }" "{ \"sqlDBName\": { \"value\": \"*\" } }" "{ \"administratorLogin\": { \"value\": \"*\" } }" "{ \"administratorLoginPassword\": { \"value\": \"*\" } }" --template-uri https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/101-sql-database/azuredeploy.json

# ADD FIREWALL RULE FOR SOURCE SQL SERVER
az sql server firewall-rule create --end-ip-address * --name * --resource-group  opttc --server * --start-ip-address *
