# pnrservice
PNR service for IRCTC train tickets. Indian Railways booking waitlist status.

## API Endpoints
Once you've registered your client, it's easy to start requesting data from Railofy.

All endpoints are only accessible via https and are located at odinsword.railofy.com

For instance: you can retrieve passenger information with a given PNR by accessing the following URL with your access_key (replace ACCESS-TOKEN with your own):

> https://odinsword.railofy.com/v1/getRailofyTravelGuarantee/?pnr=<PNR>

**Headers**
x-api-key: ACCESS_TOKEN

### Request structure
GET
/getRailofyTravelGuarantee/?pnr=8888888888

### Sample Response structure
```
{
"success": true,
"message": "Data found",
"errorCode": "NA",
"data": {
 	"pnr": "2631671201",
        "noOfPassengers": 2,
        "class": "3A",
        "trainName": "RANIKHET EXP",
        "train_no": "15014",
        "chartPrepared": false,
        "quota": "GN",
        "doj": "2019-12-15",
        "train_depart_time": "20:35",
        "arrival_date": "2020-07-29",
        "arrival_time": "23:25",
        "trainCancelled": true,
        "paxInfo": [
            {
          	"pax_no": "1",
                "booking_no": "11",
                "booking_status": "RAC",
                "booking_coach_id": "",
                "current_no": "9",
                "current_status": "RAC",
                "current_coach_id": "",
            },
            {
          	"pax_no": "2",
                "booking_no": "12",
                "booking_status": "RAC",
                "booking_coach_id": "",
                "current_no": "10",
                "current_status": "RAC",
                "current_coach_id": "",
            } ],
            "boardingStation": {
                "stationCode": "KGM",
                "stationName": "KATHGODAM"
            },
            "reservationUpto": {
                "stationCode": "DEC",
                "stationName": "DELHI CANTT"
            },
            "from": {
                "stationCode": "KGM",
                "stationName": "KATHGODAM"
            },
            "to": {
                "stationCode": "DEC",
                "stationName": "DELHI CANTT"
            },
            "tgDetails": {
 	        "tgAvailable": true,
	        "cnfTG": true,
	        "racTG": true,
	        "cnfRejectMsg": "",
	        "racRejectMsg": ""
             }
        }
}
```

## Error Responses
```
{
   "success": false,
   "message": "Invalid Access Key",
   "errorCode": 1001,
   "data": {}
}
```

```
{
   "success": false,
   "message": "Missing Parameters",
   "errorCode": 1002,
   "data": {}
}
```

```
{
   "success": false,
   "message": "Servers Down",
   "errorCode": 1003,
   "data": {}
}
```

```
{
   "success": false,
   "message": "Invalid PNR",
   "errorCode": 1004,
   "data": {}
}
```

## Limits
Please refer to the Annexure for information on rate limits that apply to API requests.

## Contact
For any queries, please contact: ankita@railofy.com
