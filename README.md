# IoT - TP

## Downloads : 
- [ ] Influxd : https://dl.influxdata.com/influxdb/releases/influxdb2-2.5.1-windows-amd64.zip
- [ ] Grafana : https://grafana.com/grafana/download?platform=windows
- [ ] NodeJS : https://nodejs.org/en

## Dependancies: 
- [ ] npm : ``` npm i --save ```
- [ ] Express : ``` npm install express --save ```
- [ ] TypeScript ``` npm i -g typescript && npm i --save-dev @types/node ```
- [ ] Dependancies for Influx : ``` npm install --save @influxdata/influxdb-client ```
- [ ] Dependancies for API : ``` npm install --save @influxdata/influxdb-client-apis ```
- [ ] Dependancies of dotenv : ``` dotenv --save ```

## Urls : 
- Influxd : http://localhost:8086
- Grafana : http://localhost:8000/

## Documentation : 
- Influxd : https://docs.influxdata.com/
- Grafana : https://grafana.com/docs/grafana/latest/
- NodeJS : https://nodejs.org/en/docs/

### First Step : Installation
Download the zip "tp-iot" and extract in a new folder. After install NodeJs, Express, and all dependancies, create the Middleware folder and run (tape enter for all parameters defaults). Navigate to where you downloaded indluxDB and execute the following command in a powershell or CMD ``` influxd.exe ``` then go to http://localhost:8086


### Second Step : InfluxD
Configure TypeScript ``` tsc --init ```. Go to http://localhost:8086/ et sign in. Copy the URL and remplace "url" by the adress on the .env file. Then, make the same for the ID of organisation. Return on influxd and create a new bucket and copy the ID too in the .env. Create a new APIToken and copy the ID. Run the MiddleWare ``` node app.js ``` then run the sensors in a new terminal tab ``` npm i ``` ``` npm run sensors ``` in the folder : tp-iot/tp-iot-main. 

### Thrid Step : Grafana
Return on http://localhost:3000/ and auth with "admin" and "admin" for both fields. Add your first data source with InfluxDB and Query language = Flux. Paste the URL = http://localhost:8086/ and disallow basic auth. Copy settings informations on .env and save & test.

Add New Dashboard > Add a new panel > Sample Query > simple query
Confirgure : "db/rp" = your bucket
Confirgure : v.timeRangeStart , stop:v.timeRangeStop = -1d 
Confirgure : "exemple-measurement" = "humidity"
Confirgure :  "exemple-filed" = "humidity"
Confirgure : "exemple-measurement" = "temperature"
Confirgure : "exemple-filed" = "Temperature"
Confirgure : Unit = temperature(°C)
Confirgure : treshold = 25
Save & Apply
