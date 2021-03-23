# opttc - create Azure SQL from ARM via Azure CLI

# paramenters for creation

RG=""
LOCATION=""
SERVERNAME=""
SQLDBNAME=""
USERNAME=""
PASSWORD=''

# CREATE RESOURCE GROUP
az group create --name $RG --location $LOCATION

# CREATE AZURE SQL 
az deployment group create --resource-group $RG  --parameters "{ \"location\": { \"value\": \"$LOCATION\" } }" "{ \"serverName\": { \"value\": \"$SERVERNAME\" } }" "{ \"sqlDBName\": { \"value\": \"$SQLDBNAME\" } }" "{ \"administratorLogin\": { \"value\": \"$USERNAME\" } }" "{ \"administratorLoginPassword\": { \"value\": \"$PASSWORD\" } }" --template-uri https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/101-sql-database/azuredeploy.json
