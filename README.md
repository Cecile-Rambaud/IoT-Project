# TP IoT - Hamza & Cécile

## Downloads : 
- [ ] Influxd : https://dl.influxdata.com/influxdb/releases/influxdb2-2.5.1-windows-amd64.zip
- [ ] Grafana : https://grafana.com/grafana/download?platform=windows
- [ ] NodeJS : https://nodejs.org/en

## Dependancies : 
- [ ] npm : ``` npm i --save ```
- [ ] Express : ``` npm install express --save ```
- [ ] TypeScript ``` npm i -g typescript && npm i --save-dev @types/node ```
- [ ] Influx CLI : ``` npm install --save @influxdata/influxdb-client ```
- [ ] Influx API : ``` npm install --save @influxdata/influxdb-client-apis ```
- [ ] dotenv : ``` dotenv --save ```

## Documentation : 
- Influxd : https://docs.influxdata.com/
- Grafana : https://grafana.com/docs/grafana/latest/
- NodeJS : https://nodejs.org/en/docs/

***

### First Step : Installation
Download the zip "tp-iot" and extract it in a new folder. After, install NodeJs, Grafana, InfluxD, and all dependancies. Then create the Middleware folder and run (enter for all parameters defaults). Return where you downloaded IndluxDB and execute the following command in a powershell or CMD ``` influxd.exe ```.

### Second Step : InfluxD
Configure TypeScript wth the command ``` tsc --init ```. Go to http://localhost:8086/ et sign in. Copy the URL and remplace "url" by the adress on the .env file. Then, make the same for the ID of organisation. Return on influxd and create a new bucket and copy the ID too in the .env. Create a new APIToken and copy the ID. Run the MiddleWare ``` node app.js ``` then, run the sensors in a new terminal tab ``` npm i ``` ``` npm run sensors ``` in the folder : tp-iot/tp-iot-main. 

### Third Step : Grafana
Return on http://localhost:3000/ and auth with "admin" and "admin" for both fields. Add your first data source > with InfluxDB > Query language > Flux. Paste the URL = http://localhost:8086/ and disallow basic auth. Copy settings informations on .env and save & test.
Add New Dashboard > Add a new panel > Sample Query > simple query :
- Configure : "db/rp" = your bucket
- Configure : v.timeRangeStart , stop:v.timeRangeStop = -1d 
- Configure : "exemple-measurement" = "humidity"
- Configure :  "exemple-filed" = "humidity"
- Configure : "exemple-measurement" = "temperature"
- Configure : "exemple-filed" = "Temperature"
- Configure : Unit = temperature(°C)
- Configure : treshold = 25
- Save & Apply



![CAPTURE 1](https://user-images.githubusercontent.com/56160891/210944691-470cf502-abce-48b4-b04c-ddde26635fff.jpg)

![CAPTURE 2](https://user-images.githubusercontent.com/56160891/210944779-303ab2a1-cf38-4dc1-8dcc-1ac1747cf15c.png)

![CAPTURE 2]220124144322352](https://user-images.githubusercontent.com/56160891/210944722-0aa8c922-97bf-4835-b888-3a12ad71fde1.png)

![CAPTURE 3](https://user-images.githubusercontent.com/56160891/210944952-b876a8c8-9c42-4de2-880a-b1266d9cfe79.png)

![CAPTURE 4](https://user-images.githubusercontent.com/56160891/210945656-9e9e9321-2979-4e61-b360-40a24adbb5bb.png)

![CAPTURE 5](https://user-images.githubusercontent.com/56160891/210945493-a45882ed-b32e-4ec7-908d-983266dd1ed8.png)

![CAPTURE 6](https://user-images.githubusercontent.com/56160891/210943221-d396f026-0c02-4da6-9afe-e6758ee5b3c6.jpg)
