# Keypilot API Documentation


## Base URL
- Production: `https://api.exp.keypilot.io`


## Common Response Format
```json
{
  "status": "success" | "error",
  "message": "Response message",
  "timestamp": "2024-01-01T00:00:00.000Z",
  "responseStatus": 200,
  "result": {},
  "isCached": false
}
```

---

## Endpoints

### Health Check
#### GET `/`
**Description:** Health check endpoint to verify API status.

**Response:**
```
Health checked!
```

---

### Constants/Autocomplete
#### GET `/constants`
**Description:** Get autocomplete data for various property-related constants.

**Query Parameters:**
- `type` (string, required): Type of autocomplete data to retrieve

**Example:**
```
GET /constants?type=location
```

---

### Index Data
#### GET `/index`
**Description:** Get sales index data with various filtering options.

**Query Parameters:**
- `type` (string): Filter by type - `all`, `year`, `quarter`, `month`

**Example:**
```
GET /index?type=year
```

---

### Feedback
#### POST `/feedback`
**Description:** Submit feedback, ratings, or bug reports.

**Query Parameters:**
- `type` (string, required): Type of feedback - `rating`, `feedback`, `Bug`

**Request Body:**
```json
{
  "feedback": "User feedback text",
  "rating": 5
}
```

---

### Rental Endpoints

#### GET `/rental/`
**Description:** Get rental transaction data with comprehensive filtering.

**Query Parameters:**
- `year` (number): Year filter (default: 2024)
- `location` (string): Location/area filter
- `version_en` (string): Version filter
- `month` (number): Month filter (default: 0)
- `property_type` (string): Property type filter
- `usage_en` (string): Usage type filter
- `limit` (number): Results limit (default: 10)
- `offset` (number): Results offset (default: 0)
- `room_en` (string): Room configuration filter
- `project` (string): Project name filter
- `isFreeHold` (string): Freehold status filter

#### GET `/rental/average`
**Description:** Get average yearly rental data.

**Query Parameters:**
- `location` (string): Location filter
- `room_en` (string): Room configuration
- `start_year` (number): Start year
- `end_year` (number): End year

eg.:
```curl
curl --location 'http://127.0.0.1:5001/psyched-span-426722-q0/us-central1/dev/api/rental/average?end_year=2024&start_year=2019' \
--header 'Authorization: ${API_KEY}'
```
<details>
<summary>Response Example</summary>

```json
    "status": "success",
    "message": "Data fetched successfully",
    "timestamp": "2025-09-24T16:13:32.961Z",
    "responseStatus": 200,
    "result": [
        {
            "Year": 2019,
            "total_transaction_yearly": 657022,
            "total_transaction_new_yearly": 325519,
            "total_transaction_renewal_yearly": 331503,
            "renewal_ratio_yearly": 0.4981788651300439,
            "avg_rent_yearly": 6501.722543670142,
            "avg_rent_new_yearly": 6024.746293452892,
            "avg_rent_renewal_yearly": 6987.686989878793,
            "total_rent_yearly": 4278490409.416667,
            "month_data": [
                {
                    "Month": 1,
                    "Total_Transactions": 93740,
                    "Total_Monthly_Rent": 627961166.5833335,
                    "Avg_Monthly_Rent": 6699.181396709234,
                    "Total_Monthly_Rent_New": 220780449.91666666,
                    "Avg_Monthly_Rent_New": 5859.664788913068,
                    "Total_Monthly_Rent_Renewal": 407180716.66666675,
                    "Avg_Monthly_Rent_Renewal": 7263.431682096839,
                    "Total_Transactions_New": 37681,
                    "Total_Transactions_Renewal": 56059,
                    "Renewal_Ratio": 0.5980264561553232
                },
                {
                    "Month": 2,
                    "Total_Transactions": 47910,
                    "Total_Monthly_Rent": 318225639.50000006,
                    "Avg_Monthly_Rent": 6642.154863285324,
                    "Total_Monthly_Rent_New": 151369700.58333337,
                    "Avg_Monthly_Rent_New": 6132.051876983325,
                    "Total_Monthly_Rent_Renewal": 166855938.91666657,
                    "Avg_Monthly_Rent_Renewal": 7184.324603516323,
                    "Total_Transactions_New": 24685,
                    "Total_Transactions_Renewal": 23225,
                    "Renewal_Ratio": 0.48476309747443125
                },
                {
                    "Month": 3,
                    "Total_Transactions": 49508,
                    "Total_Monthly_Rent": 338296030.91666675,
                    "Avg_Monthly_Rent": 6833.158901928309,
                    "Total_Monthly_Rent_New": 157805850.5,
                    "Avg_Monthly_Rent_New": 6192.593120904132,
                    "Total_Monthly_Rent_Renewal": 180490180.4166667,
                    "Avg_Monthly_Rent_Renewal": 7512.598560527228,
                    "Total_Transactions_New": 25483,
                    "Total_Transactions_Renewal": 24025,
                    "Renewal_Ratio": 0.4852751070534055
                },
                {
                    "Month": 4,
                    "Total_Transactions": 55011,
                    "Total_Monthly_Rent": 343608423.0833334,
                    "Avg_Monthly_Rent": 6246.176638914638,
                    "Total_Monthly_Rent_New": 156285775.58333334,
                    "Avg_Monthly_Rent_New": 5879.162456582528,
                    "Total_Monthly_Rent_Renewal": 187322647.50000018,
                    "Avg_Monthly_Rent_Renewal": 6589.371306458421,
                    "Total_Transactions_New": 26583,
                    "Total_Transactions_Renewal": 28428,
                    "Renewal_Ratio": 0.5167693733980476
                },
                {
                    "Month": 5,
                    "Total_Transactions": 50326,
                    "Total_Monthly_Rent": 319272806.6666667,
                    "Avg_Monthly_Rent": 6344.0926492601575,
                    "Total_Monthly_Rent_New": 146459844.08333337,
                    "Avg_Monthly_Rent_New": 6050.809505611787,
                    "Total_Monthly_Rent_Renewal": 172812962.5833333,
                    "Avg_Monthly_Rent_Renewal": 6615.863197554968,
                    "Total_Transactions_New": 24205,
                    "Total_Transactions_Renewal": 26121,
                    "Renewal_Ratio": 0.5190358860231292
                },
                {
                    "Month": 6,
                    "Total_Transactions": 46773,
                    "Total_Monthly_Rent": 297793193.75000006,
                    "Avg_Monthly_Rent": 6366.775570307657,
                    "Total_Monthly_Rent_New": 137494781.3333333,
                    "Avg_Monthly_Rent_New": 6164.026779043006,
                    "Total_Monthly_Rent_Renewal": 160298412.41666672,
                    "Avg_Monthly_Rent_Renewal": 6551.616970477241,
                    "Total_Transactions_New": 22306,
                    "Total_Transactions_Renewal": 24467,
                    "Renewal_Ratio": 0.5231009342997028
                },
                {
                    "Month": 7,
                    "Total_Transactions": 55354,
                    "Total_Monthly_Rent": 359848374.2499999,
                    "Avg_Monthly_Rent": 6500.855841492937,
                    "Total_Monthly_Rent_New": 171089960.50000006,
                    "Avg_Monthly_Rent_New": 6185.912231542411,
                    "Total_Monthly_Rent_Renewal": 188758413.75,
                    "Avg_Monthly_Rent_Renewal": 6815.367336438476,
                    "Total_Transactions_New": 27658,
                    "Total_Transactions_Renewal": 27696,
                    "Renewal_Ratio": 0.5003432452939264
                },
                {
                    "Month": 8,
                    "Total_Transactions": 51409,
                    "Total_Monthly_Rent": 345825976.8333335,
                    "Avg_Monthly_Rent": 6726.953973688137,
                    "Total_Monthly_Rent_New": 165573461.00000015,
                    "Avg_Monthly_Rent_New": 6489.768392584176,
                    "Total_Monthly_Rent_Renewal": 180252515.83333325,
                    "Avg_Monthly_Rent_Renewal": 6960.6315969004245,
                    "Total_Transactions_New": 25513,
                    "Total_Transactions_Renewal": 25896,
                    "Renewal_Ratio": 0.5037250286914743
                },
                {
                    "Month": 9,
                    "Total_Transactions": 51036,
                    "Total_Monthly_Rent": 344935555.75000006,
                    "Avg_Monthly_Rent": 6758.671442707106,
                    "Total_Monthly_Rent_New": 166606546.58333325,
                    "Avg_Monthly_Rent_New": 6084.972482955928,
                    "Total_Monthly_Rent_Renewal": 178329009.16666672,
                    "Avg_Monthly_Rent_Renewal": 7538.4261568594275,
                    "Total_Transactions_New": 27380,
                    "Total_Transactions_Renewal": 23656,
                    "Renewal_Ratio": 0.4635159495258249
                },
                {
                    "Month": 10,
                    "Total_Transactions": 54317,
                    "Total_Monthly_Rent": 344486474.16666675,
                    "Avg_Monthly_Rent": 6342.148391234175,
                    "Total_Monthly_Rent_New": 164836861.0833333,
                    "Avg_Monthly_Rent_New": 5652.453915483619,
                    "Total_Monthly_Rent_Renewal": 179649613.08333334,
                    "Avg_Monthly_Rent_Renewal": 7141.705946465247,
                    "Total_Transactions_New": 29162,
                    "Total_Transactions_Renewal": 25155,
                    "Renewal_Ratio": 0.46311467864572786
                },
                {
                    "Month": 11,
                    "Total_Transactions": 50628,
                    "Total_Monthly_Rent": 327076945.91666675,
                    "Avg_Monthly_Rent": 6460.523948025098,
                    "Total_Monthly_Rent_New": 160518874.1666666,
                    "Avg_Monthly_Rent_New": 5951.977239299443,
                    "Total_Monthly_Rent_Renewal": 166558071.75,
                    "Avg_Monthly_Rent_Renewal": 7040.243120720264,
                    "Total_Transactions_New": 26969,
                    "Total_Transactions_Renewal": 23659,
                    "Renewal_Ratio": 0.46731057912617524
                },
                {
                    "Month": 12,
                    "Total_Transactions": 51010,
                    "Total_Monthly_Rent": 311159821.9999999,
                    "Avg_Monthly_Rent": 6099.976906488925,
                    "Total_Monthly_Rent_New": 157700478.83333334,
                    "Avg_Monthly_Rent_New": 5653.562731531275,
                    "Total_Monthly_Rent_Renewal": 153459343.16666666,
                    "Avg_Monthly_Rent_Renewal": 6638.663400530658,
                    "Total_Transactions_New": 27894,
                    "Total_Transactions_Renewal": 23116,
                    "Renewal_Ratio": 0.4531660458733582
                }
            ]
        },
        {
            "Year": 2020,
            "total_transaction_yearly": 657137,
            "total_transaction_new_yearly": 332411,
            "total_transaction_renewal_yearly": 324726,
            "renewal_ratio_yearly": 0.49155137629798645,
            "avg_rent_yearly": 5922.327082851713,
            "avg_rent_new_yearly": 5355.451596357752,
            "avg_rent_renewal_yearly": 6520.331976307222,
            "total_rent_yearly": 3914334383.916666,
            "month_data": [
                {
                    "Month": 1,
                    "Total_Transactions": 90777,
                    "Total_Monthly_Rent": 591309256.6666671,
                    "Avg_Monthly_Rent": 6516.666189101223,
                    "Total_Monthly_Rent_New": 204975316.66666672,
                    "Avg_Monthly_Rent_New": 5939.4197985183455,
                    "Total_Monthly_Rent_Renewal": 386333940.00000006,
                    "Avg_Monthly_Rent_Renewal": 6870.968395966349,
                    "Total_Transactions_New": 34547,
                    "Total_Transactions_Renewal": 56230,
                    "Renewal_Ratio": 0.6194300318362581
                },
                {
                    "Month": 2,
                    "Total_Transactions": 52394,
                    "Total_Monthly_Rent": 321664531.24999994,
                    "Avg_Monthly_Rent": 6139.456248926383,
                    "Total_Monthly_Rent_New": 145965536.0833333,
                    "Avg_Monthly_Rent_New": 5426.026396168664,
                    "Total_Monthly_Rent_Renewal": 175698995.16666675,
                    "Avg_Monthly_Rent_Renewal": 6892.318969349861,
                    "Total_Transactions_New": 26901,
                    "Total_Transactions_Renewal": 25493,
                    "Renewal_Ratio": 0.4865633469481238
                },
                {
                    "Month": 3,
                    "Total_Transactions": 49130,
                    "Total_Monthly_Rent": 301706939.16666657,
                    "Avg_Monthly_Rent": 6140.992044914854,
                    "Total_Monthly_Rent_New": 150146027.24999994,
                    "Avg_Monthly_Rent_New": 5604.345759770074,
                    "Total_Monthly_Rent_Renewal": 151560911.91666666,
                    "Avg_Monthly_Rent_Renewal": 6784.5880261724615,
                    "Total_Transactions_New": 26791,
                    "Total_Transactions_Renewal": 22339,
                    "Renewal_Ratio": 0.4546916344392428
                },
                {
                    "Month": 4,
                    "Total_Transactions": 43266,
                    "Total_Monthly_Rent": 253736781.99999997,
                    "Avg_Monthly_Rent": 5864.847956730771,
                    "Total_Monthly_Rent_New": 94350182.99999999,
                    "Avg_Monthly_Rent_New": 5164.779012480839,
                    "Total_Monthly_Rent_Renewal": 159386599.00000003,
                    "Avg_Monthly_Rent_Renewal": 6376.484197471596,
                    "Total_Transactions_New": 18269,
                    "Total_Transactions_Renewal": 24997,
                    "Renewal_Ratio": 0.5777515832293255
                },
                {
                    "Month": 5,
                    "Total_Transactions": 41479,
                    "Total_Monthly_Rent": 239307633.33333322,
                    "Avg_Monthly_Rent": 5769.507530096274,
                    "Total_Monthly_Rent_New": 85252006.83333331,
                    "Avg_Monthly_Rent_New": 5054.6665974939715,
                    "Total_Monthly_Rent_Renewal": 154055626.50000003,
                    "Avg_Monthly_Rent_Renewal": 6259.370490004876,
                    "Total_Transactions_New": 16867,
                    "Total_Transactions_Renewal": 24612,
                    "Renewal_Ratio": 0.5933604956725089
                },
                {
                    "Month": 6,
                    "Total_Transactions": 44581,
                    "Total_Monthly_Rent": 252547855.2500001,
                    "Avg_Monthly_Rent": 5665.175424527243,
                    "Total_Monthly_Rent_New": 108740222.66666667,
                    "Avg_Monthly_Rent_New": 5123.455647694436,
                    "Total_Monthly_Rent_Renewal": 143807632.58333328,
                    "Avg_Monthly_Rent_Renewal": 6157.466606008707,
                    "Total_Transactions_New": 21226,
                    "Total_Transactions_Renewal": 23355,
                    "Renewal_Ratio": 0.5238778851977299
                },
                {
                    "Month": 7,
                    "Total_Transactions": 56069,
                    "Total_Monthly_Rent": 338676022.16666657,
                    "Avg_Monthly_Rent": 6040.343543966663,
                    "Total_Monthly_Rent_New": 158554331.99999997,
                    "Avg_Monthly_Rent_New": 5717.9967543005505,
                    "Total_Monthly_Rent_Renewal": 180121690.1666667,
                    "Avg_Monthly_Rent_Renewal": 6355.740655139967,
                    "Total_Transactions_New": 27729,
                    "Total_Transactions_Renewal": 28340,
                    "Renewal_Ratio": 0.5054486436355206
                },
                {
                    "Month": 8,
                    "Total_Transactions": 52914,
                    "Total_Monthly_Rent": 315246755.4999999,
                    "Avg_Monthly_Rent": 5957.831827717193,
                    "Total_Monthly_Rent_New": 156630508.83333334,
                    "Avg_Monthly_Rent_New": 5429.510150905896,
                    "Total_Monthly_Rent_Renewal": 158616246.66666666,
                    "Avg_Monthly_Rent_Renewal": 6591.159221552741,
                    "Total_Transactions_New": 28849,
                    "Total_Transactions_Renewal": 24065,
                    "Renewal_Ratio": 0.45479457232490456
                },
                {
                    "Month": 9,
                    "Total_Transactions": 54946,
                    "Total_Monthly_Rent": 342598594.9166665,
                    "Avg_Monthly_Rent": 6235.527636216927,
                    "Total_Monthly_Rent_New": 176605378.25000006,
                    "Avg_Monthly_Rent_New": 5571.499093002712,
                    "Total_Monthly_Rent_Renewal": 165993216.6666667,
                    "Avg_Monthly_Rent_Renewal": 7141.028895102888,
                    "Total_Transactions_New": 31700,
                    "Total_Transactions_Renewal": 23246,
                    "Renewal_Ratio": 0.423069923197321
                },
                {
                    "Month": 10,
                    "Total_Transactions": 60197,
                    "Total_Monthly_Rent": 337364245.8333331,
                    "Avg_Monthly_Rent": 5604.522731677603,
                    "Total_Monthly_Rent_New": 176236636.24999994,
                    "Avg_Monthly_Rent_New": 5060.4903305002035,
                    "Total_Monthly_Rent_Renewal": 161127609.58333334,
                    "Avg_Monthly_Rent_Renewal": 6351.358334318788,
                    "Total_Transactions_New": 34827,
                    "Total_Transactions_Renewal": 25370,
                    "Renewal_Ratio": 0.42144957389903154
                },
                {
                    "Month": 11,
                    "Total_Transactions": 56077,
                    "Total_Monthly_Rent": 325735476.25000006,
                    "Avg_Monthly_Rent": 5808.925122603657,
                    "Total_Monthly_Rent_New": 173751271.74999994,
                    "Avg_Monthly_Rent_New": 5323.751317523055,
                    "Total_Monthly_Rent_Renewal": 151984204.5,
                    "Avg_Monthly_Rent_Renewal": 6484.521055550814,
                    "Total_Transactions_New": 32638,
                    "Total_Transactions_Renewal": 23439,
                    "Renewal_Ratio": 0.41797885050912137
                },
                {
                    "Month": 12,
                    "Total_Transactions": 55307,
                    "Total_Monthly_Rent": 294440291.5833335,
                    "Avg_Monthly_Rent": 5324.128737741772,
                    "Total_Monthly_Rent_New": 155488822.66666666,
                    "Avg_Monthly_Rent_New": 4849.478297934274,
                    "Total_Monthly_Rent_Renewal": 138951468.91666672,
                    "Avg_Monthly_Rent_Renewal": 5978.978869047617,
                    "Total_Transactions_New": 32067,
                    "Total_Transactions_Renewal": 23240,
                    "Renewal_Ratio": 0.4201999746867485
                }
            ]
        },
        {
            "Year": 2021,
            "total_transaction_yearly": 769038,
            "total_transaction_new_yearly": 430963,
            "total_transaction_renewal_yearly": 338075,
            "renewal_ratio_yearly": 0.4357635040699662,
            "avg_rent_yearly": 5895.343634677872,
            "avg_rent_new_yearly": 5265.34223224842,
            "avg_rent_renewal_yearly": 6709.940443675016,
            "total_rent_yearly": 4531779972.999999,
            "month_data": [
                {
                    "Month": 1,
                    "Total_Transactions": 94638,
                    "Total_Monthly_Rent": 552581621.9166672,
                    "Avg_Monthly_Rent": 5839.144725116414,
                    "Total_Monthly_Rent_New": 222845068.0833334,
                    "Avg_Monthly_Rent_New": 5019.033064939942,
                    "Total_Monthly_Rent_Renewal": 329736553.83333325,
                    "Avg_Monthly_Rent_Renewal": 6564.011502833405,
                    "Total_Transactions_New": 44402,
                    "Total_Transactions_Renewal": 50236,
                    "Renewal_Ratio": 0.5308227139204125
                },
                {
                    "Month": 2,
                    "Total_Transactions": 55892,
                    "Total_Monthly_Rent": 319135182.91666645,
                    "Avg_Monthly_Rent": 5709.9565747019515,
                    "Total_Monthly_Rent_New": 173003203.91666678,
                    "Avg_Monthly_Rent_New": 5382.632896196966,
                    "Total_Monthly_Rent_Renewal": 146131979,
                    "Avg_Monthly_Rent_Renewal": 6152.925431578949,
                    "Total_Transactions_New": 32141,
                    "Total_Transactions_Renewal": 23751,
                    "Renewal_Ratio": 0.42494453589064624
                },
                {
                    "Month": 3,
                    "Total_Transactions": 60227,
                    "Total_Monthly_Rent": 431698925.1666665,
                    "Avg_Monthly_Rent": 7167.863668565042,
                    "Total_Monthly_Rent_New": 174174959.08333346,
                    "Avg_Monthly_Rent_New": 5080.505179923967,
                    "Total_Monthly_Rent_Renewal": 257523966.08333337,
                    "Avg_Monthly_Rent_Renewal": 9926.147320510838,
                    "Total_Transactions_New": 34283,
                    "Total_Transactions_Renewal": 25944,
                    "Renewal_Ratio": 0.4307702525445398
                },
                {
                    "Month": 4,
                    "Total_Transactions": 54809,
                    "Total_Monthly_Rent": 305870238,
                    "Avg_Monthly_Rent": 5580.86080245224,
                    "Total_Monthly_Rent_New": 165959425.16666675,
                    "Avg_Monthly_Rent_New": 5182.34527750021,
                    "Total_Monthly_Rent_Renewal": 139910812.8333333,
                    "Avg_Monthly_Rent_Renewal": 6141.017988558723,
                    "Total_Transactions_New": 32025,
                    "Total_Transactions_Renewal": 22784,
                    "Renewal_Ratio": 0.41569815176339653
                },
                {
                    "Month": 5,
                    "Total_Transactions": 47373,
                    "Total_Monthly_Rent": 270386661.5,
                    "Avg_Monthly_Rent": 5707.852093052712,
                    "Total_Monthly_Rent_New": 142521654.58333337,
                    "Avg_Monthly_Rent_New": 5293.676580742612,
                    "Total_Monthly_Rent_Renewal": 127865006.91666672,
                    "Avg_Monthly_Rent_Renewal": 6253.179133248564,
                    "Total_Transactions_New": 26924,
                    "Total_Transactions_Renewal": 20449,
                    "Renewal_Ratio": 0.43165938403732085
                },
                {
                    "Month": 6,
                    "Total_Transactions": 52858,
                    "Total_Monthly_Rent": 301041783.1666665,
                    "Avg_Monthly_Rent": 5695.5082330608975,
                    "Total_Monthly_Rent_New": 165831862.5,
                    "Avg_Monthly_Rent_New": 5345.6212526594045,
                    "Total_Monthly_Rent_Renewal": 135209920.6666666,
                    "Avg_Monthly_Rent_Renewal": 6192.6317059021085,
                    "Total_Transactions_New": 31024,
                    "Total_Transactions_Renewal": 21834,
                    "Renewal_Ratio": 0.4130689772598282
                },
                {
                    "Month": 7,
                    "Total_Transactions": 61072,
                    "Total_Monthly_Rent": 360935823.583333,
                    "Avg_Monthly_Rent": 5910.101743598982,
                    "Total_Monthly_Rent_New": 182800263.9166668,
                    "Avg_Monthly_Rent_New": 5658.049520758533,
                    "Total_Monthly_Rent_Renewal": 178135559.6666667,
                    "Avg_Monthly_Rent_Renewal": 6193.219054572423,
                    "Total_Transactions_New": 32309,
                    "Total_Transactions_Renewal": 28763,
                    "Renewal_Ratio": 0.4709686926905947
                },
                {
                    "Month": 8,
                    "Total_Transactions": 61818,
                    "Total_Monthly_Rent": 392378890.9166666,
                    "Avg_Monthly_Rent": 6347.426936225743,
                    "Total_Monthly_Rent_New": 185830425.83333343,
                    "Avg_Monthly_Rent_New": 5330.3050751035025,
                    "Total_Monthly_Rent_Renewal": 206548465.08333328,
                    "Avg_Monthly_Rent_Renewal": 7662.998630382626,
                    "Total_Transactions_New": 34864,
                    "Total_Transactions_Renewal": 26954,
                    "Renewal_Ratio": 0.43602187065256076
                },
                {
                    "Month": 9,
                    "Total_Transactions": 69468,
                    "Total_Monthly_Rent": 401809398.16666657,
                    "Avg_Monthly_Rent": 5784.093369129191,
                    "Total_Monthly_Rent_New": 218291462.83333343,
                    "Avg_Monthly_Rent_New": 5291.657685283946,
                    "Total_Monthly_Rent_Renewal": 183517935.33333328,
                    "Avg_Monthly_Rent_Renewal": 6504.037969001039,
                    "Total_Transactions_New": 41252,
                    "Total_Transactions_Renewal": 28216,
                    "Renewal_Ratio": 0.40617262624517764
                },
                {
                    "Month": 10,
                    "Total_Transactions": 71925,
                    "Total_Monthly_Rent": 424697553.83333325,
                    "Avg_Monthly_Rent": 5904.974191948684,
                    "Total_Monthly_Rent_New": 236709721.91666684,
                    "Avg_Monthly_Rent_New": 5575.675364315886,
                    "Total_Monthly_Rent_Renewal": 187987831.91666672,
                    "Avg_Monthly_Rent_Renewal": 6379.3888936021,
                    "Total_Transactions_New": 42455,
                    "Total_Transactions_Renewal": 29470,
                    "Renewal_Ratio": 0.4097323600973236
                },
                {
                    "Month": 11,
                    "Total_Transactions": 70222,
                    "Total_Monthly_Rent": 403956276,
                    "Avg_Monthly_Rent": 5752.88780654533,
                    "Total_Monthly_Rent_New": 211343401.58333334,
                    "Avg_Monthly_Rent_New": 5099.616378720974,
                    "Total_Monthly_Rent_Renewal": 192612874.41666666,
                    "Avg_Monthly_Rent_Renewal": 6693.757581812915,
                    "Total_Transactions_New": 41444,
                    "Total_Transactions_Renewal": 28778,
                    "Renewal_Ratio": 0.4098145880208482
                },
                {
                    "Month": 12,
                    "Total_Transactions": 68736,
                    "Total_Monthly_Rent": 367287617.8333332,
                    "Avg_Monthly_Rent": 5343.4534717372735,
                    "Total_Monthly_Rent_New": 186361565.25,
                    "Avg_Monthly_Rent_New": 4924.988510835095,
                    "Total_Monthly_Rent_Renewal": 180926052.58333325,
                    "Avg_Monthly_Rent_Renewal": 5855.970112096495,
                    "Total_Transactions_New": 37840,
                    "Total_Transactions_Renewal": 30896,
                    "Renewal_Ratio": 0.449487895716946
                }
            ]
        },
        {
            "Year": 2022,
            "total_transaction_yearly": 894100,
            "total_transaction_new_yearly": 466199,
            "total_transaction_renewal_yearly": 427901,
            "renewal_ratio_yearly": 0.47631988099414485,
            "avg_rent_yearly": 5667.292021131579,
            "avg_rent_new_yearly": 5190.875650253166,
            "avg_rent_renewal_yearly": 6188.4433917617425,
            "total_rent_yearly": 5070436791.166666,
            "month_data": [
                {
                    "Month": 1,
                    "Total_Transactions": 99443,
                    "Total_Monthly_Rent": 571897865.4999998,
                    "Avg_Monthly_Rent": 5751.243128953428,
                    "Total_Monthly_Rent_New": 218393924.66666678,
                    "Avg_Monthly_Rent_New": 4892.446619921294,
                    "Total_Monthly_Rent_Renewal": 353503940.8333333,
                    "Avg_Monthly_Rent_Renewal": 6450.80184002433,
                    "Total_Transactions_New": 44642,
                    "Total_Transactions_Renewal": 54801,
                    "Renewal_Ratio": 0.5510795128867794
                },
                {
                    "Month": 2,
                    "Total_Transactions": 70813,
                    "Total_Monthly_Rent": 396049218.3333333,
                    "Avg_Monthly_Rent": 5593.362497116576,
                    "Total_Monthly_Rent_New": 202169235.74999997,
                    "Avg_Monthly_Rent_New": 5230.228068246495,
                    "Total_Monthly_Rent_Renewal": 193879982.58333337,
                    "Avg_Monthly_Rent_Renewal": 6029.918905960047,
                    "Total_Transactions_New": 38658,
                    "Total_Transactions_Renewal": 32155,
                    "Renewal_Ratio": 0.4540832897914225
                },
                {
                    "Month": 3,
                    "Total_Transactions": 73321,
                    "Total_Monthly_Rent": 402908216.2499999,
                    "Avg_Monthly_Rent": 5495.277025736848,
                    "Total_Monthly_Rent_New": 193721858.33333328,
                    "Avg_Monthly_Rent_New": 4895.056432933248,
                    "Total_Monthly_Rent_Renewal": 209186357.91666663,
                    "Avg_Monthly_Rent_Renewal": 6199.2163915560295,
                    "Total_Transactions_New": 39575,
                    "Total_Transactions_Renewal": 33746,
                    "Renewal_Ratio": 0.46025013297690975
                },
                {
                    "Month": 4,
                    "Total_Transactions": 70396,
                    "Total_Monthly_Rent": 390121734.25,
                    "Avg_Monthly_Rent": 5541.816782913799,
                    "Total_Monthly_Rent_New": 192267527.83333337,
                    "Avg_Monthly_Rent_New": 5080.528692351057,
                    "Total_Monthly_Rent_Renewal": 197854206.41666663,
                    "Avg_Monthly_Rent_Renewal": 6078.09678104776,
                    "Total_Transactions_New": 37844,
                    "Total_Transactions_Renewal": 32552,
                    "Renewal_Ratio": 0.46241263708165237
                },
                {
                    "Month": 5,
                    "Total_Transactions": 59633,
                    "Total_Monthly_Rent": 330593836.4999998,
                    "Avg_Monthly_Rent": 5543.899860812985,
                    "Total_Monthly_Rent_New": 158323371.99999997,
                    "Avg_Monthly_Rent_New": 5132.86989787648,
                    "Total_Monthly_Rent_Renewal": 172270464.5,
                    "Avg_Monthly_Rent_Renewal": 5984.314603814221,
                    "Total_Transactions_New": 30846,
                    "Total_Transactions_Renewal": 28787,
                    "Renewal_Ratio": 0.48273606895510873
                },
                {
                    "Month": 6,
                    "Total_Transactions": 64538,
                    "Total_Monthly_Rent": 358234075.24999994,
                    "Avg_Monthly_Rent": 5550.746463323933,
                    "Total_Monthly_Rent_New": 187742796.6666667,
                    "Avg_Monthly_Rent_New": 5177.254961439114,
                    "Total_Monthly_Rent_Renewal": 170491278.58333334,
                    "Avg_Monthly_Rent_Renewal": 6029.753442381371,
                    "Total_Transactions_New": 36263,
                    "Total_Transactions_Renewal": 28275,
                    "Renewal_Ratio": 0.4381139793609966
                },
                {
                    "Month": 7,
                    "Total_Transactions": 68549,
                    "Total_Monthly_Rent": 414884625.6666665,
                    "Avg_Monthly_Rent": 6052.557014408608,
                    "Total_Monthly_Rent_New": 198610019.7500001,
                    "Avg_Monthly_Rent_New": 5834.606925675674,
                    "Total_Monthly_Rent_Renewal": 216274605.91666666,
                    "Avg_Monthly_Rent_Renewal": 6267.557478675826,
                    "Total_Transactions_New": 34041,
                    "Total_Transactions_Renewal": 34508,
                    "Renewal_Ratio": 0.503406322484646
                },
                {
                    "Month": 8,
                    "Total_Transactions": 71903,
                    "Total_Monthly_Rent": 409394660.66666657,
                    "Avg_Monthly_Rent": 5694.103600471036,
                    "Total_Monthly_Rent_New": 201212693.24999994,
                    "Avg_Monthly_Rent_New": 5166.453377753811,
                    "Total_Monthly_Rent_Renewal": 208181967.41666672,
                    "Avg_Monthly_Rent_Renewal": 6317.733898296511,
                    "Total_Transactions_New": 38951,
                    "Total_Transactions_Renewal": 32952,
                    "Renewal_Ratio": 0.45828407715950653
                },
                {
                    "Month": 9,
                    "Total_Transactions": 76727,
                    "Total_Monthly_Rent": 448707394.6666667,
                    "Avg_Monthly_Rent": 5848.484068020472,
                    "Total_Monthly_Rent_New": 217686734.75,
                    "Avg_Monthly_Rent_New": 5325.017973336595,
                    "Total_Monthly_Rent_Renewal": 231020659.91666666,
                    "Avg_Monthly_Rent_Renewal": 6445.529265014973,
                    "Total_Transactions_New": 40885,
                    "Total_Transactions_Renewal": 35842,
                    "Renewal_Ratio": 0.4671367315286666
                },
                {
                    "Month": 10,
                    "Total_Transactions": 83035,
                    "Total_Monthly_Rent": 466159573.25000006,
                    "Avg_Monthly_Rent": 5614.351117066122,
                    "Total_Monthly_Rent_New": 227204790.50000006,
                    "Avg_Monthly_Rent_New": 5150.16752425424,
                    "Total_Monthly_Rent_Renewal": 238954782.7500001,
                    "Avg_Monthly_Rent_Renewal": 6140.586492008018,
                    "Total_Transactions_New": 44117,
                    "Total_Transactions_Renewal": 38918,
                    "Renewal_Ratio": 0.46869392424881073
                },
                {
                    "Month": 11,
                    "Total_Transactions": 81316,
                    "Total_Monthly_Rent": 458999233.08333343,
                    "Avg_Monthly_Rent": 5644.913826782435,
                    "Total_Monthly_Rent_New": 221113079.41666692,
                    "Avg_Monthly_Rent_New": 5075.358752620545,
                    "Total_Monthly_Rent_Renewal": 237886153.6666667,
                    "Avg_Monthly_Rent_Renewal": 6302.2877567601,
                    "Total_Transactions_New": 43568,
                    "Total_Transactions_Renewal": 37748,
                    "Renewal_Ratio": 0.4642136848836637
                },
                {
                    "Month": 12,
                    "Total_Transactions": 74426,
                    "Total_Monthly_Rent": 422486357.7499997,
                    "Avg_Monthly_Rent": 5676.748867972696,
                    "Total_Monthly_Rent_New": 196200397.25000024,
                    "Avg_Monthly_Rent_New": 5330.518576629445,
                    "Total_Monthly_Rent_Renewal": 226285960.4999999,
                    "Avg_Monthly_Rent_Renewal": 6015.5238456017205,
                    "Total_Transactions_New": 36809,
                    "Total_Transactions_Renewal": 37617,
                    "Renewal_Ratio": 0.5054282105715745
                }
            ]
        },
        {
            "Year": 2023,
            "total_transaction_yearly": 996848,
            "total_transaction_new_yearly": 487979,
            "total_transaction_renewal_yearly": 508869,
            "renewal_ratio_yearly": 0.5095200529491646,
            "avg_rent_yearly": 6461.564977339622,
            "avg_rent_new_yearly": 5721.320430019608,
            "avg_rent_renewal_yearly": 7132.047131233108,
            "total_rent_yearly": 6406725786.083341,
            "month_data": [
                {
                    "Month": 1,
                    "Total_Transactions": 109144,
                    "Total_Monthly_Rent": 663528905.6666673,
                    "Avg_Monthly_Rent": 6079.4453667818025,
                    "Total_Monthly_Rent_New": 261138770.08333308,
                    "Avg_Monthly_Rent_New": 5588.605518936232,
                    "Total_Monthly_Rent_Renewal": 402390135.58333343,
                    "Avg_Monthly_Rent_Renewal": 6446.906812088779,
                    "Total_Transactions_New": 46728,
                    "Total_Transactions_Renewal": 62416,
                    "Renewal_Ratio": 0.571868357399399
                },
                {
                    "Month": 2,
                    "Total_Transactions": 75344,
                    "Total_Monthly_Rent": 450614333.83333325,
                    "Avg_Monthly_Rent": 5980.918131099966,
                    "Total_Monthly_Rent_New": 214412436.3333335,
                    "Avg_Monthly_Rent_New": 5821.6789664223,
                    "Total_Monthly_Rent_Renewal": 236201897.50000006,
                    "Avg_Monthly_Rent_Renewal": 6133.202573223933,
                    "Total_Transactions_New": 36831,
                    "Total_Transactions_Renewal": 38513,
                    "Renewal_Ratio": 0.5111621363346783
                },
                {
                    "Month": 3,
                    "Total_Transactions": 79351,
                    "Total_Monthly_Rent": 536875070.2500001,
                    "Avg_Monthly_Rent": 6766.081945984777,
                    "Total_Monthly_Rent_New": 215026488.33333343,
                    "Avg_Monthly_Rent_New": 5584.523382851998,
                    "Total_Monthly_Rent_Renewal": 321848581.9166667,
                    "Avg_Monthly_Rent_Renewal": 7879.9476524499705,
                    "Total_Transactions_New": 38507,
                    "Total_Transactions_Renewal": 40844,
                    "Renewal_Ratio": 0.5147257123413693
                },
                {
                    "Month": 4,
                    "Total_Transactions": 73407,
                    "Total_Monthly_Rent": 707557595.2500006,
                    "Avg_Monthly_Rent": 9638.961328093075,
                    "Total_Monthly_Rent_New": 185923463.25000024,
                    "Avg_Monthly_Rent_New": 5581.946176594214,
                    "Total_Monthly_Rent_Renewal": 521634131.99999994,
                    "Avg_Monthly_Rent_Renewal": 13008.981295825231,
                    "Total_Transactions_New": 33309,
                    "Total_Transactions_Renewal": 40098,
                    "Renewal_Ratio": 0.546242183987903
                },
                {
                    "Month": 5,
                    "Total_Transactions": 72339,
                    "Total_Monthly_Rent": 429473993.9999999,
                    "Avg_Monthly_Rent": 5936.963380748975,
                    "Total_Monthly_Rent_New": 205131577.0833334,
                    "Avg_Monthly_Rent_New": 5554.304589064589,
                    "Total_Monthly_Rent_Renewal": 224342416.91666678,
                    "Avg_Monthly_Rent_Renewal": 6336.103508251663,
                    "Total_Transactions_New": 36932,
                    "Total_Transactions_Renewal": 35407,
                    "Renewal_Ratio": 0.48945935111074246
                },
                {
                    "Month": 6,
                    "Total_Transactions": 71212,
                    "Total_Monthly_Rent": 431119722.83333313,
                    "Avg_Monthly_Rent": 6054.031944522458,
                    "Total_Monthly_Rent_New": 206083763.1666668,
                    "Avg_Monthly_Rent_New": 5815.3327830765475,
                    "Total_Monthly_Rent_Renewal": 225035959.66666666,
                    "Avg_Monthly_Rent_Renewal": 6290.489172769797,
                    "Total_Transactions_New": 35438,
                    "Total_Transactions_Renewal": 35774,
                    "Renewal_Ratio": 0.5023591529517497
                },
                {
                    "Month": 7,
                    "Total_Transactions": 77202,
                    "Total_Monthly_Rent": 480057105.7500002,
                    "Avg_Monthly_Rent": 6218.275744485173,
                    "Total_Monthly_Rent_New": 208744441.41666692,
                    "Avg_Monthly_Rent_New": 5726.0853495176725,
                    "Total_Monthly_Rent_Renewal": 271312664.3333333,
                    "Avg_Monthly_Rent_Renewal": 6658.63310099969,
                    "Total_Transactions_New": 36456,
                    "Total_Transactions_Renewal": 40746,
                    "Renewal_Ratio": 0.5277842542939302
                },
                {
                    "Month": 8,
                    "Total_Transactions": 80552,
                    "Total_Monthly_Rent": 504439683.83333373,
                    "Avg_Monthly_Rent": 6262.364015758137,
                    "Total_Monthly_Rent_New": 237313678.5,
                    "Avg_Monthly_Rent_New": 5804.135263042045,
                    "Total_Monthly_Rent_Renewal": 267126005.33333337,
                    "Avg_Monthly_Rent_Renewal": 6734.721796423287,
                    "Total_Transactions_New": 40888,
                    "Total_Transactions_Renewal": 39664,
                    "Renewal_Ratio": 0.49240242327937234
                },
                {
                    "Month": 9,
                    "Total_Transactions": 87180,
                    "Total_Monthly_Rent": 554925038.8333346,
                    "Avg_Monthly_Rent": 6365.279179093065,
                    "Total_Monthly_Rent_New": 270143584.583333,
                    "Avg_Monthly_Rent_New": 6015.757016508558,
                    "Total_Monthly_Rent_Renewal": 284781454.24999994,
                    "Avg_Monthly_Rent_Renewal": 6736.56276316412,
                    "Total_Transactions_New": 44906,
                    "Total_Transactions_Renewal": 42274,
                    "Renewal_Ratio": 0.4849047946776784
                },
                {
                    "Month": 10,
                    "Total_Transactions": 92953,
                    "Total_Monthly_Rent": 567150027.0000015,
                    "Avg_Monthly_Rent": 6101.5365672605185,
                    "Total_Monthly_Rent_New": 272724168.08333296,
                    "Avg_Monthly_Rent_New": 5772.306560910393,
                    "Total_Monthly_Rent_Renewal": 294425858.9166667,
                    "Avg_Monthly_Rent_Renewal": 6441.874169492759,
                    "Total_Transactions_New": 47248,
                    "Total_Transactions_Renewal": 45705,
                    "Renewal_Ratio": 0.4917001065054382
                },
                {
                    "Month": 11,
                    "Total_Transactions": 90677,
                    "Total_Monthly_Rent": 550988451.166668,
                    "Avg_Monthly_Rent": 6076.788070790734,
                    "Total_Monthly_Rent_New": 255684887.66666648,
                    "Avg_Monthly_Rent_New": 5478.335783053364,
                    "Total_Monthly_Rent_Renewal": 295303563.5,
                    "Avg_Monthly_Rent_Renewal": 6711.597161299119,
                    "Total_Transactions_New": 46676,
                    "Total_Transactions_Renewal": 44001,
                    "Renewal_Ratio": 0.48524984284879297
                },
                {
                    "Month": 12,
                    "Total_Transactions": 87487,
                    "Total_Monthly_Rent": 529995857.66666764,
                    "Avg_Monthly_Rent": 6058.134053456785,
                    "Total_Monthly_Rent_New": 260507630.2499998,
                    "Avg_Monthly_Rent_New": 5912.833770257387,
                    "Total_Monthly_Rent_Renewal": 269488227.4166666,
                    "Avg_Monthly_Rent_Renewal": 6205.54556880896,
                    "Total_Transactions_New": 44060,
                    "Total_Transactions_Renewal": 43427,
                    "Renewal_Ratio": 0.49638231965892077
                }
            ]
        },
        {
            "Year": 2024,
            "total_transaction_yearly": 1132019,
            "total_transaction_new_yearly": 577054,
            "total_transaction_renewal_yearly": 554965,
            "renewal_ratio_yearly": 0.48938621844272706,
            "avg_rent_yearly": 6302.829652836086,
            "avg_rent_new_yearly": 5670.917932188601,
            "avg_rent_renewal_yearly": 6970.160836135248,
            "total_rent_yearly": 7146038323.85831,
            "month_data": [
                {
                    "Month": 1,
                    "Total_Transactions": 121523,
                    "Total_Monthly_Rent": 753588202.1082984,
                    "Avg_Monthly_Rent": 6201.453299990921,
                    "Total_Monthly_Rent_New": 293306591.2499994,
                    "Avg_Monthly_Rent_New": 5546.540179837751,
                    "Total_Monthly_Rent_Renewal": 460281610.85829645,
                    "Avg_Monthly_Rent_Renewal": 6706.027519534605,
                    "Total_Transactions_New": 52885,
                    "Total_Transactions_Renewal": 68638,
                    "Renewal_Ratio": 0.5648148910082865
                },
                {
                    "Month": 2,
                    "Total_Transactions": 92201,
                    "Total_Monthly_Rent": 562388514.250002,
                    "Avg_Monthly_Rent": 6099.6585059652925,
                    "Total_Monthly_Rent_New": 251993390.3333333,
                    "Avg_Monthly_Rent_New": 5541.360974894629,
                    "Total_Monthly_Rent_Renewal": 310395123.91666657,
                    "Avg_Monthly_Rent_Renewal": 6643.020308542892,
                    "Total_Transactions_New": 45475,
                    "Total_Transactions_Renewal": 46726,
                    "Renewal_Ratio": 0.5067840912788365
                },
                {
                    "Month": 3,
                    "Total_Transactions": 88407,
                    "Total_Monthly_Rent": 532424974.9166674,
                    "Avg_Monthly_Rent": 6022.498189225464,
                    "Total_Monthly_Rent_New": 247469124.49999985,
                    "Avg_Monthly_Rent_New": 5398.776659103803,
                    "Total_Monthly_Rent_Renewal": 284955850.4166666,
                    "Avg_Monthly_Rent_Renewal": 6694.132926533235,
                    "Total_Transactions_New": 45839,
                    "Total_Transactions_Renewal": 42568,
                    "Renewal_Ratio": 0.4815003336839843
                },
                {
                    "Month": 4,
                    "Total_Transactions": 82243,
                    "Total_Monthly_Rent": 491377222.1666668,
                    "Avg_Monthly_Rent": 5974.7722838290265,
                    "Total_Monthly_Rent_New": 203754345.91666684,
                    "Avg_Monthly_Rent_New": 5313.574973052383,
                    "Total_Monthly_Rent_Renewal": 287622876.24999994,
                    "Avg_Monthly_Rent_Renewal": 6552.370973437217,
                    "Total_Transactions_New": 38346,
                    "Total_Transactions_Renewal": 43897,
                    "Renewal_Ratio": 0.5337475529832326
                },
                {
                    "Month": 5,
                    "Total_Transactions": 86508,
                    "Total_Monthly_Rent": 512125114.6666673,
                    "Avg_Monthly_Rent": 5920.179349941237,
                    "Total_Monthly_Rent_New": 242143997.16666687,
                    "Avg_Monthly_Rent_New": 5177.114452378914,
                    "Total_Monthly_Rent_Renewal": 269981117.5,
                    "Avg_Monthly_Rent_Renewal": 6794.883786776737,
                    "Total_Transactions_New": 46774,
                    "Total_Transactions_Renewal": 39734,
                    "Renewal_Ratio": 0.4593101216072502
                },
                {
                    "Month": 6,
                    "Total_Transactions": 80490,
                    "Total_Monthly_Rent": 504938599.00000036,
                    "Avg_Monthly_Rent": 6273.4643549348975,
                    "Total_Monthly_Rent_New": 229868901.75000012,
                    "Avg_Monthly_Rent_New": 5732.391564837906,
                    "Total_Monthly_Rent_Renewal": 275069697.25000006,
                    "Avg_Monthly_Rent_Renewal": 6810.678846439536,
                    "Total_Transactions_New": 40102,
                    "Total_Transactions_Renewal": 40388,
                    "Renewal_Ratio": 0.5017766182134427
                },
                {
                    "Month": 7,
                    "Total_Transactions": 92714,
                    "Total_Monthly_Rent": 570652848.9166687,
                    "Avg_Monthly_Rent": 6155.046745512134,
                    "Total_Monthly_Rent_New": 261338067.4166665,
                    "Avg_Monthly_Rent_New": 5440.6892496287355,
                    "Total_Monthly_Rent_Renewal": 309314781.49999994,
                    "Avg_Monthly_Rent_Renewal": 6923.046207390496,
                    "Total_Transactions_New": 48035,
                    "Total_Transactions_Renewal": 44679,
                    "Renewal_Ratio": 0.4819013309748258
                },
                {
                    "Month": 8,
                    "Total_Transactions": 97393,
                    "Total_Monthly_Rent": 618073374.3333347,
                    "Avg_Monthly_Rent": 6346.243781145614,
                    "Total_Monthly_Rent_New": 303119850.333333,
                    "Avg_Monthly_Rent_New": 5663.6743335824585,
                    "Total_Monthly_Rent_Renewal": 314953524.00000006,
                    "Avg_Monthly_Rent_Renewal": 7178.91876367615,
                    "Total_Transactions_New": 53520,
                    "Total_Transactions_Renewal": 43873,
                    "Renewal_Ratio": 0.45047385335701745
                },
                {
                    "Month": 9,
                    "Total_Transactions": 100088,
                    "Total_Monthly_Rent": 672676608.2500017,
                    "Avg_Monthly_Rent": 6721.0531872908,
                    "Total_Monthly_Rent_New": 331681877.41666603,
                    "Avg_Monthly_Rent_New": 6073.20242825405,
                    "Total_Monthly_Rent_Renewal": 340994730.8333334,
                    "Avg_Monthly_Rent_Renewal": 7499.169379018128,
                    "Total_Transactions_New": 54616,
                    "Total_Transactions_Renewal": 45472,
                    "Renewal_Ratio": 0.4543201982255615
                },
                {
                    "Month": 10,
                    "Total_Transactions": 103553,
                    "Total_Monthly_Rent": 660360138.1666679,
                    "Avg_Monthly_Rent": 6377.210412039272,
                    "Total_Monthly_Rent_New": 323035191.0833327,
                    "Avg_Monthly_Rent_New": 5770.3403073011605,
                    "Total_Monthly_Rent_Renewal": 337324947.0833332,
                    "Avg_Monthly_Rent_Renewal": 7091.425897311916,
                    "Total_Transactions_New": 55983,
                    "Total_Transactions_Renewal": 47570,
                    "Renewal_Ratio": 0.45937828937838593
                },
                {
                    "Month": 11,
                    "Total_Transactions": 95890,
                    "Total_Monthly_Rent": 687104753.0000013,
                    "Avg_Monthly_Rent": 7165.775892456745,
                    "Total_Monthly_Rent_New": 321347371.1666662,
                    "Avg_Monthly_Rent_New": 6478.516413988681,
                    "Total_Monthly_Rent_Renewal": 365757381.83333343,
                    "Avg_Monthly_Rent_Renewal": 7902.287605775811,
                    "Total_Transactions_New": 49603,
                    "Total_Transactions_Renewal": 46287,
                    "Renewal_Ratio": 0.48270935446866203
                },
                {
                    "Month": 12,
                    "Total_Transactions": 91009,
                    "Total_Monthly_Rent": 580327974.0833328,
                    "Avg_Monthly_Rent": 6376.599831701625,
                    "Total_Monthly_Rent_New": 271348908.5000003,
                    "Avg_Monthly_Rent_New": 5914.833649402737,
                    "Total_Monthly_Rent_Renewal": 308979065.58333343,
                    "Avg_Monthly_Rent_Renewal": 6845.967819186255,
                    "Total_Transactions_New": 45876,
                    "Total_Transactions_Renewal": 45133,
                    "Renewal_Ratio": 0.49591798613323956
                }
            ]
        }
    ],
    "isCached": false
}
```

</details>


#### GET `/rental/segment`
**Description:** Get rental market segmentation data.

**Query Parameters:**
- `start_year` (number): Start year
- `end_year` (number): End year
- `location` (string): Location filter
- `property_type` (string): Property type
- `usage_en` (string): Usage type
- `room_en` (string): Room configuration
- `isFreeHold` (string): Freehold status
- `project` (string): Project filter

#### GET `/rental/last`
**Description:** Get most recent rental transactions.

**Query Parameters:**
- `limit` (number): Results limit (default: 10)
- `offset` (number): Results offset (default: 0)

#### GET `/rental/index`
**Description:** Get rental price index with quartile analysis.

**Query Parameters:**
- `location` (string): Location filter
- `start_year` (number): Start year
- `end_year` (number): End year

#### GET `/rental/comp`
**Description:** Get rental price compression analysis.

**Query Parameters:**
- `location` (string): Location filter
- `property_type` (string): Property type
- `usage_en` (string): Usage type
- `room_en` (string): Room configuration
- `isFreeHold` (string): Freehold status
- `project` (string): Project filter
- `group_en` (string): Group filter

#### GET `/rental/rentIndex`
**Description:** Get comprehensive rental index data.

**Query Parameters:**
- `year` (number): Year filter
- `month` (number): Month filter
- `start_year` (number): Start year
- `end_year` (number): End year
- `location` (string): Location filter
- `property_type` (string): Property type
- `usage_en` (string): Usage type
- `room_en` (string): Room configuration
- `isFreeHold` (string): Freehold status
- `project` (string): Project filter

#### GET `/rental/pages/:page`
**Description:** Get paginated rental transactions.

**Path Parameters:**
- `page` (number): Page number

**Query Parameters:**
- `GROUP_EN` (string): Group filter
- `USAGE_EN` (string): Usage filter
- `PARKING` (string): Parking availability - `Yes`, `No`
- `start_date` (string): Start date filter
- `end_date` (string): End date filter
- `orderBy` (string): Sort field
- `sequence` (string): Sort order
- `year` (string): Year filter

#### GET `/rental/marketPulse/pages/:page`
**Description:** Get rental market pulse data with pagination.

**Path Parameters:**
- `page` (number): Page number

**Query Parameters:**
- `order` (string): Sort order
- `location` (string): Location filter

---

### Transaction Endpoints

#### GET `/transaction/growth`
**Description:** Get transaction growth comparison data.

**Query Parameters:**
- `start_date` (string): Start date (YYYY-MM-DD)
- `end_date` (string): End date (YYYY-MM-DD)
- `location` (string): Location filter
- `property_type` (string): Property type
- `usage_en` (string): Usage type
- `room` (string): Room configuration
- `project` (string): Project filter
- `isFreehold` (string): Freehold status
- `group_en` (string): Group filter
- `property_sub_type` (string): Property sub-type
- `is_offplan` (string): Off-plan status - `Off-Plan`, `Ready`

#### GET `/transaction/types`
**Description:** Get transaction type breakdown.

**Query Parameters:**
- `year` (number): Year filter
- `month` (number): Month filter
- `start_year` (number): Start year
- `end_year` (number): End year
- `location` (string): Location filter
- `property_type` (string): Property type
- `usage_en` (string): Usage type
- `room_en` (string): Room configuration
- `isFreeHold` (string): Freehold status
- `project` (string): Project filter
- `group_en` (string): Group filter
- `IS_OFFPLAN_EN` (string): Off-plan status - `Off-Plan`, `Ready`
- `PROP_SB_TYPE_EN` (string): Property sub-type

#### GET `/transaction/trends`
**Description:** Get transaction trend analysis.

**Query Parameters:**
- `year` (number): Year filter
- `start_year` (number): Start year
- `end_year` (number): End year
- `location` (string): Location filter
- `property_type` (string): Property type
- `usage_en` (string): Usage type
- `room_en` (string): Room configuration
- `isFreeHold` (string): Freehold status
- `project` (string): Project filter
- `group_en` (string): Group filter
- `PROP_SB_TYPE_EN` (string): Property sub-type
- `IS_OFFPLAN_EN` (string): Off-plan status
- `start_date` (string): Start date
- `end_date` (string): End date

#### GET `/transaction/last`
**Description:** Get most recent transactions.

**Query Parameters:**
- `limit` (number): Results limit (default: 10)
- `offset` (number): Results offset (default: 0)
- `location` (string): Location filter
- `property_type` (string): Property type
- `usage_en` (string): Usage type
- `room_en` (string): Room configuration
- `isFreeHold` (string): Freehold status
- `project` (string): Project filter
- `group_en` (string): Group filter
- `PROP_SB_TYPE_EN` (string): Property sub-type
- `IS_OFFPLAN_EN` (string): Off-plan status

#### GET `/transaction/index`
**Description:** Get transaction index with quartile analysis.

**Query Parameters:**
- `IS_OFFPLAN_EN` (string): Off-plan status
- `location` (string): Location filter
- `start_year` (number): Start year
- `end_year` (number): End year

#### GET `/transaction/comp`
**Description:** Get price comparison and change analysis.

**Query Parameters:**
- `location` (string): Location filter
- `property_type` (string): Property type
- `usage_en` (string): Usage type
- `room_en` (string): Room configuration
- `isFreeHold` (string): Freehold status
- `project` (string): Project filter
- `group_en` (string): Group filter
- `PROP_SB_TYPE_EN` (string): Property sub-type
- `IS_OFFPLAN_EN` (string): Off-plan status
- `start_year` (number): Start year
- `end_year` (number): End year

#### GET `/transaction/salesIndex`
**Description:** Get comprehensive sales index data.

**Query Parameters:**
- `year` (number): Year filter
- `month` (number): Month filter
- `start_year` (number): Start year
- `end_year` (number): End year
- `location` (string): Location filter
- `property_type` (string): Property type
- `usage_en` (string): Usage type
- `room_en` (string): Room configuration
- `isFreeHold` (string): Freehold status
- `project` (string): Project filter
- `group_en` (string): Group filter
- `PROP_SB_TYPE_EN` (string): Property sub-type
- `IS_OFFPLAN_EN` (string): Off-plan status

#### GET `/transaction/offplan`
**Description:** Get off-plan property data.

**Query Parameters:**
- `start_year` (number): Start year
- `end_year` (number): End year

#### GET `/transaction/pages/:page`
**Description:** Get paginated sales transactions.

**Path Parameters:**
- `page` (number): Page number

**Query Parameters:**
- `GROUP_EN` (string): Group filter
- `USAGE_EN` (string): Usage filter
- `start_date` (string): Start date
- `end_date` (string): End date
- `orderBy` (string): Sort field
- `sequence` (string): Sort order
- `location` (string): Location filter
- `IS_OFFPLAN_EN` (string): Off-plan status
- `start_year` (number): Start year
- `end_year` (number): End year
- `MinPrice` (number): Minimum price filter
- `MaxPrice` (number): Maximum price filter

#### GET `/transaction/marketPulse/pages/:page`
**Description:** Get sales and rental market pulse data.

**Path Parameters:**
- `page` (number): Page number

**Query Parameters:**
- `limit` (number): Results limit
- `offset` (number): Results offset
- `location` (string): Location filter
- `order` (string): Sort order

---

### Broker Endpoints

#### GET `/brokers/:brn`
**Description:** Get broker data by Broker Registration Number (BRN).

**Path Parameters:**
- `brn` (string): Broker Registration Number

#### GET `/brokers/page/:page`
**Description:** Get paginated broker listings.

**Path Parameters:**
- `page` (number): Page number

---

### Office Endpoints

#### GET `/offices/:orn`
**Description:** Get office data by Office Registration Number (ORN).

**Path Parameters:**
- `orn` (string): Office Registration Number

#### GET `/offices/page/:page`
**Description:** Get paginated office listings.

**Path Parameters:**
- `page` (number): Page number

---

### Project Endpoints

#### GET `/projects/page/:page`
**Description:** Get paginated project listings.

**Path Parameters:**
- `page` (number): Page number

**Query Parameters:**
- `order` (string): Sort field - `completion_date`, `project_name`, `no_of_units`, `no_of_villas`, `percent_completed`, `project_status`
- `sortBy` (string): Sort direction - `asc`, `desc`
- `projectStatus` (string): Project status filter
- `start_date` (string): Start date filter
- `end_date` (string): End date filter

#### GET `/projects/details`
**Description:** Get detailed project information with filters.

**Query Parameters:**
- `location` (string): Location filter
- `start_year` (number): Start year (default: 2014)
- `end_year` (number): End year (default: 2024)
- `completion_date` (string): Completion date filter
- `PercentageFilter` (string): Completion percentage range (e.g., "0-50")

#### GET `/projects/details/w/`
**Description:** Get project details without project status filter.

**Query Parameters:**
- Same as `/projects/details`

#### GET `/projects/futureSupply`
**Description:** Get future property supply data.

**Query Parameters:**
- `location` (string): Location filter

#### GET `/projects/deliveredUnits`
**Description:** Get delivered units data.

**Query Parameters:**
- `location` (string): Location filter

#### GET `/projects/compPercent`
**Description:** Get properties by completion percentage.

**Query Parameters:**
- `location` (string): Location filter

#### GET `/projects/:projectId`
**Description:** Get specific project details by ID.

**Path Parameters:**
- `projectId` (string): Project identifier

---

### Developer Endpoints

#### GET `/developers/total`
**Description:** Get total number of developers.

#### GET `/developers/page/:page`
**Description:** Get paginated developer listings.

**Path Parameters:**
- `page` (number): Page number

#### GET `/developers/:developerId`
**Description:** Get specific developer details by ID.

**Path Parameters:**
- `developerId` (string): Developer identifier

---

### Calculator Endpoints

#### POST `/calculator/transaction`
**Description:** Calculate transaction-related metrics.

**Request Body:**
```json
{
  "location": "string",
  "usage": "string",
  "project": "string",
  "propType": "string",
  "prop_sub_type": "string",
  "room": "string",
  "IS_OFFPLAN_EN": "Off-Plan" | "Ready",
  "start_year": 2014,
  "end_year": 2025
}
```

#### POST `/calculator/rental`
**Description:** Calculate rental-related metrics.

**Request Body:**
```json
{
  "location": "string",
  "usage": "string",
  "project": "string",
  "propType": "string",
  "saleType": "string",
  "start_year": 2014,
  "end_year": 2025,
  "prop_sub_type": "string"
}
```

---

### Chat/AI Endpoints

#### POST `/chat/c/`
**Description:** Main chat handler for AI interactions.

#### GET `/chat/id/:id`
**Description:** Get session ID for chat.

**Path Parameters:**
- `id` (string): Session identifier

#### POST `/chat/autoComplete`
**Description:** Get AI autocomplete suggestions.

#### POST `/chat/summary`
**Description:** Get AI-generated summary.

#### POST `/chat/s/calculator`
**Description:** Get calculator summary via AI.

#### POST `/chat/v2/c/`
**Description:** Chat handler version 2.

#### GET `/chat/v2/history/:id/:sessionId`
**Description:** Get chat history.

**Path Parameters:**
- `id` (string): User identifier
- `sessionId` (string): Session identifier

---

### Insights Endpoints

#### GET `/insights/transaction`
**Description:** Get comprehensive transaction insights combining multiple data sources.

**Query Parameters:**
- All transaction-related filters from individual endpoints
- `year`, `start_year`, `end_year` (number): Date filters
- `location`, `property_type`, `usage_en`, `room_en`, `isFreeHold`, `project`, `group_en`, `PROP_SB_TYPE_EN` (string): Property filters
- `IS_OFFPLAN_EN` (string): Off-plan status
- `limit`, `offset`, `month` (number): Pagination and time filters

#### GET `/insights/rental`
**Description:** Get comprehensive rental insights combining multiple data sources.

**Query Parameters:**
- All rental-related filters from individual endpoints
- Similar filter structure as transaction insights

---

### Lead Magnet Endpoints

#### PUT `/leadMagnet/`
**Description:** Update lead magnet data.

---

### Authentication Endpoints

#### POST `/auth/create`
**Description:** Create API authorization token.

#### GET `/auth/refresh`
**Description:** Refresh authentication token.

---

### User Data Endpoints

#### GET `/userData/check/:brn`
**Description:** Check if user exists by BRN.

**Path Parameters:**
- `brn` (string): Broker Registration Number

#### GET `/userData/checkHandle/:handle`
**Description:** Check if user handle exists.

**Path Parameters:**
- `handle` (string): User handle

#### GET `/userData/id/:brn`
**Description:** Get user ID data by BRN.

**Path Parameters:**
- `brn` (string): Broker Registration Number

#### GET `/userData/pf/:id`
**Description:** Get Property Finder data by ID.

**Path Parameters:**
- `id` (string): User identifier

#### GET `/userData/bayut/:id`
**Description:** Get Bayut data by ID.

**Path Parameters:**
- `id` (string): User identifier

#### GET `/userData/pf/property/:id`
**Description:** Get Property Finder property data.

**Path Parameters:**
- `id` (string): Property identifier

#### GET `/userData/bayut/property/:id`
**Description:** Get Bayut property data.

**Path Parameters:**
- `id` (string): Property identifier

#### GET `/userData/user`
**Description:** Get user data with multiple ID options.

**Query Parameters:**
- `brn` (string): Broker Registration Number
- `pfId` (string): Property Finder ID
- `bayutId` (string): Bayut ID

#### POST `/userData/user/:brn`
**Description:** Create new user data.

**Path Parameters:**
- `brn` (string): Broker Registration Number

#### GET `/userData/:id`
**Description:** Get user data by ID.

**Path Parameters:**
- `id` (string): User identifier

---

## Common Filters

### Location Filters
- `location` / `area_en` / `AREA_EN`: Geographic location filter
- Used across most endpoints

### Property Type Filters
- `property_type` / `PROP_TYPE_EN`: Property type classification
- `PROP_SB_TYPE_EN` / `prop_sub_type`: Property sub-type
- `usage_en` / `USAGE_EN`: Property usage type
- `room_en` / `ROOMS_EN`: Room configuration

### Date/Time Filters
- `year`: Specific year
- `start_year`, `end_year`: Year range
- `month`: Specific month
- `start_date`, `end_date`: Date range (YYYY-MM-DD format)
- `completion_date`: Project completion date

### Transaction Filters
- `IS_OFFPLAN_EN` / `is_offplan`: Off-plan status (`Off-Plan`, `Ready`)
- `IS_READY` / `is_ready`: Ready status
- `isFreeHold` / `IS_FREE_HOLD`: Freehold/Leasehold status
- `first_sale`: First sale indicator
- `TransactionType`: Type of transaction

### Project/Development Filters
- `project`: Project name
- `group_en` / `GROUP_EN`: Developer group
- `projectStatus`: Project status
- `PercentageFilter`: Completion percentage range

### Pagination Filters
- `limit`: Maximum number of results
- `offset`: Results offset
- `page`: Page number (used in paginated endpoints)

### Sorting Filters
- `order` / `orderBy`: Sort field
- `sortBy` / `sequence`: Sort direction (`asc`, `desc`)

### Price Filters
- `MinPrice`: Minimum price threshold
- `MaxPrice`: Maximum price threshold

### Special Filters
- `version_en`: Version/model filter
- `PARKING`: Parking availability (`Yes`, `No`)
- `type`: Generic type filter (used in various contexts)

---

## Error Handling

### Common Error Responses
- **400 Bad Request**: Invalid parameters or missing required fields
- **401 Unauthorized**: Authentication failed
- **403 Forbidden**: Access denied (CORS or permission issues)
- **404 Not Found**: Resource not found
- **500 Internal Server Error**: Server-side errors

### Error Response Format
```json
{
  "status": "error",
  "message": "Error description",
  "responseStatus": 500,
  "result": null,
  "timestamp": "2024-01-01T00:00:00.000Z",
  "isCached": false
}
```

---

## Caching

The API implements caching mechanisms:
- Cache keys are generated based on request path, query parameters, body, and path parameters
- Cache status is indicated in response headers:
  - `X-Cache-internal`: `HIT` or `MISS`
  - `X-OpenAI-Token-Usage`: Token usage for AI endpoints
- Cache duration varies by endpoint (default: 5 minutes in non-production)


----

---


# Keypilot DLD Scraper — API Documentation

This document collects the curl examples found in `apis.txt` and provides a brief description, method, request body and example curl commands for each endpoint.

Notes:
- The examples below use the exact curl invocation from `apis.txt`. In many cases it's useful to add `-H "Content-Type: application/json"` when sending JSON bodies; an improved curl example is provided where appropriate.
- If an endpoint appears to be misspelled (for example `muncipility`), the documented path matches the raw example — verify the correct path with the server if calls fail.

---

## 1) Project lookup

- Endpoint: `https://api.v2.keypilot.io/v1/property/project`
- Method: POST
- Description: Lookup property information by project and unit. The example passes a project number, unit number and a tabMethod flag.

Request body (JSON):
# Keypilot DLD Scraper — API Documentation

This document collects the curl examples found in `apis.txt` and provides a brief description, method, request body and example curl commands for each endpoint.

Notes:

- The examples below use the exact curl invocation from `apis.txt`. In many cases it's useful to add `-H "Content-Type: application/json"` when sending JSON bodies; an improved curl example is provided where appropriate.
- If an endpoint appears to be misspelled (for example `muncipility`), the documented path matches the raw example — verify the correct path with the server if calls fail.

---

## 1) Project lookup

- Endpoint: `https://api.v2.keypilot.io/v1/property/project`
- Method: POST
- Description: Lookup property information by project and unit. The example passes a project number, unit number and a tabMethod flag.

Request body (JSON):
```json
{
	"projectNumber": "1868",
	"unitNumber": "1001",
	"tabMethod": "unit"
}
```

Original curl (from `apis.txt`):
```bash
curl -X POST 'https://api.v2.keypilot.io/v1/property/project' \
	-H "Content-Type: application/json" \
	-d '{"projectNumber":"1868","unitNumber":"1001","tabMethod":"unit"}'
```

<details>
<summary>Response (example)</summary>

```json
{
    "status": "success",
    "message": "Report sent successfully",
    "responseStatus": 200,
    "result": {
        "bigQueryResult": [
            {
                "propertyId": 1600510545,
                "projectId": 51963138,
                "projectNameEn": "ELITE BUSINESS BAY RESIDENCE",
                "landNumber": 110,
                "landSubNumber": 0,
                "parentProjectId": 53216779,
                "projectContext": {
                    "subType": "Flat",
                    "rooms": "Studio",
                    "location": {
                        "buildingNumber": "1",
                        "unitNumber": "1001"
                    },
                    "floor": "10",
                    "parking": {
                        "unitParkingNumber": "B1-26",
                        "parkingAllocationType": null,
                        "parkingAllocationTypeAr": "nan",
                        "parkingAllocationTypeEn": "nan"
                    },
                    "area": {
                        "actualArea": 45.86,
                        "commonArea": 0.11,
                        "unitBalconyArea": 11.16,
                        "actualCommonArea": 42
                    },
                    "propertyType": "Unit"
                },
                "masterProjectEn": "Business Bay",
                "landType": "Commercial"
            }
        ],
        "projectDetails": {
            "status": 200,
            "timestamp": "2025-08-31T12:28:45.331Z",
            "responseCode": "Success",
            "result": {
                "project": {
                    "location": {
                        "coordinates": {
                            "latitude": 25.17975427,
                            "longitude": 55.2657036
                        },
                        "street": "Elite Business Bay Residence, Business Bay",
                        "state": "Dubai",
                        "country": "United Arab Emirates"
                    },
                    "title": {
                        "number": "1868",
                        "name": "Elite Business Bay Residence",
                        "totalArea": 39893.19,
                        "totalUnits": 540,
                        "completion": 100,
                        "status": "Finished",
                        "completionDate": "2021-01-31T00:00:00",
                        "startDate": "2017-03-01T00:00:00",
                        "registrationDate": "2017-03-08T00:00:00",
                        "escrow": {
                            "agent": "Mashreq Bank Psc",
                            "account": "019500000152"
                        },
                        "developer": {
                            "name": "Range 4 Developments L.L.C",
                            "logo": "https://mobile.dubailand.gov.ae/Repository/developers/1046.png",
                            "contact": {
                                "phone": "971-4-2349755",
                                "email": "legal@triplanet-group.com",
                                "website": null
                            }
                        },
                        "buildings": [
                            {
                                "name": "Elite Business Bay Residence",
                                "floorCount": 31
                            }
                        ],
                        "media": {
                            "url": null
                        },
                        "unitTypes": [
                            {
                                "type": "Commercial",
                                "rooms": [
                                    {
                                        "type": "NA",
                                        "count": "11"
                                    }
                                ]
                            },
                            {
                                "type": "Residential",
                                "rooms": [
                                    {
                                        "type": "Studio",
                                        "count": "322"
                                    },
                                    {
                                        "type": "1 B/R",
                                        "count": "115"
                                    },
                                    {
                                        "type": "2 B/R",
                                        "count": "46"
                                    },
                                    {
                                        "type": "4 B/R",
                                        "count": "46"
                                    }
                                ]
                            }
                        ],
                        "sizes": [
                            82.41,
                            56.62,
                            86.8,
                            124.75,
                            203.53
                        ],
                        "inspections": [
                            {
                                "number": "331555317",
                                "date": "2020-11-12T00:00:00",
                                "progress": 100,
                                "media": [
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/756/Photos/thumb15-03-20-01-3-01-IMG_6629.JPG"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/756/Photos/thumb15-03-20-01-3-21-IMG_6617.JPG"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/756/Photos/thumb15-02-20-01-2-09-7.jpeg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/756/Photos/thumb15-01-20-01-1-36-4.jpeg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/756/Photos/thumb15-02-20-01-2-34-IMG_E6602.JPG"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/756/Photos/thumb15-02-20-01-2-48-IMG_6610.JPG"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/756/Photos/thumb15-02-20-01-2-02-6.jpeg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/756/Photos/thumb15-01-20-01-1-51-5.jpeg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/756/Photos/thumb15-02-20-01-2-17-8.jpeg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/756/Photos/thumb15-02-20-01-2-26-9.jpg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/756/Photos/thumb15-01-20-01-1-18-1.jpeg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/756/Photos/thumb15-01-20-01-1-28-2.jpeg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/756/Photos/thumb15-03-20-01-3-09-IMG_6645.JPG"
                                    }
                                ]
                            },
                            {
                                "number": "316597770",
                                "date": "2020-07-06T00:00:00",
                                "progress": 85.52,
                                "media": [
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/529/Photos/thumb13-00-20-09-0-55-20200707-floor 4 (11).jpeg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/529/Photos/thumb13-59-20-08-59-10-20200705_103100.jpg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/529/Photos/thumb13-00-20-09-0-07-20200707-floor 1  (3).jpeg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/529/Photos/thumb13-00-20-09-0-14-20200707-floor 1  (4).jpeg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/529/Photos/thumb13-59-20-08-59-34-20200705_102838.jpg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/529/Photos/thumb13-59-20-08-59-45-20200705_102845.jpg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/529/Photos/thumb13-01-20-09-1-00-20200707-floor B2 (6).jpeg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/529/Photos/thumb13-59-20-08-59-23-20200705_102833.jpg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/529/Photos/thumb13-59-20-08-59-56-20200705_103221.jpg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/529/Photos/thumb13-00-20-09-0-39-20200707-floor 1  (6).jpeg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/529/Photos/thumb13-00-20-09-0-46-20200707-floor 1  (18).jpeg"
                                    }
                                ]
                            },
                            {
                                "number": "309766635",
                                "date": "2020-04-09T00:00:00",
                                "progress": 60.24,
                                "media": [
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/295/Photos/thumb13-55-20-12-55-34-02-ext view.JPG"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/295/Photos/thumb13-57-20-12-57-44-08-int fns.jpeg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/295/Photos/thumb13-57-20-12-57-56-10-int fns.jpeg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/295/Photos/thumb13-57-20-12-57-38-07-int fns.jpeg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/295/Photos/thumb13-55-20-12-55-13-01-ext view.JPG"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/295/Photos/thumb13-56-20-12-56-11-04-ext view.JPG"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/295/Photos/thumb13-57-20-12-57-32-06-int fns.jpeg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/295/Photos/thumb13-55-20-12-55-51-03-ext view.JPG"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/295/Photos/thumb13-57-20-12-57-50-09-int fns.jpeg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/295/Photos/thumb13-56-20-12-56-41-05-ext view.JPG"
                                    }
                                ]
                            },
                            {
                                "number": "301676465",
                                "date": "2020-02-02T00:00:00",
                                "progress": 51.24,
                                "media": [
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/1/Photos/thumb10-48-20-09-48-23-IMG_3937.JPG"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/1/Photos/thumb10-48-20-09-48-38-IMG_3942.JPG"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/1/Photos/thumb10-51-20-09-51-10-IMG_3966.JPG"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/1/Photos/thumb10-49-20-09-49-17-IMG_3945.JPG"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/1/Photos/thumb10-50-20-09-50-12-IMG_3987.JPG"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/1/Photos/thumb10-50-20-09-50-00-IMG_3959.JPG"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/1/Photos/thumb10-49-20-09-49-29-IMG_3965.JPG"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/1/Photos/thumb10-50-20-09-50-23-IMG_4000.JPG"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/1/Photos/thumb10-48-20-09-48-15-IMG_3935.JPG"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/1/Photos/thumb10-51-20-09-51-31-IMG_4020.JPG"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2020/1868/1/Photos/thumb10-51-20-09-51-41-IMG_4046.JPG"
                                    }
                                ]
                            },
                            {
                                "number": "233972428",
                                "date": "2019-01-13T00:00:00",
                                "progress": 21.29,
                                "media": [
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2018/1868/1254/Photos/thumb24-51-19-08-51-26-02 - Structure (1).jpg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2018/1868/1254/Photos/thumb24-51-19-08-51-42-02 - Structure (3).jpg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2018/1868/1254/Photos/thumb24-51-19-08-51-09-01 - Ext View (2).jpg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2018/1868/1254/Photos/thumb24-51-19-08-51-15-01 - Ext View (1).jpg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2018/1868/1254/Photos/thumb24-51-19-08-51-32-02 - Structure (2).jpg"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2018/1868/1254/Photos/thumb24-51-19-08-51-51-02 - Structure (4).jpg"
                                    }
                                ]
                            },
                            {
                                "number": "144833812",
                                "date": "2017-10-18T00:00:00",
                                "progress": 4.4,
                                "media": [
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2017/1868/814/Photos/thumb19-32-17-10-32-00-01-enabling works (5).JPG"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2017/1868/814/Photos/thumb19-31-17-10-31-42-01-enabling works (1).JPG"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2017/1868/814/Photos/thumb19-32-17-10-32-09-01-enabling works main (3).JPG"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2017/1868/814/Photos/thumb19-31-17-10-31-54-01-enabling works (4).JPG"
                                    },
                                    {
                                        "url": "https://realestateims.dubailand.gov.ae/ProjectsInspectionsUploads/2017/1868/814/Photos/thumb19-31-17-10-31-48-01-enabling works (2).JPG"
                                    }
                                ]
                            }
                        ]
                    }
                }
            }
        },
        "propertyStatus": {
            "propInfo": {
                "Result": {
                    "DeveloperArabic": "رينج 4 للتطوير ش.ذ.م.م",
                    "DeveloperEnglish": "RANGE 4 DEVELOPMENTS L.L.C",
                    "LandStatus": "PREMISED",
                    "LandTypeArabic": "تجارى",
                    "LandTypeEnglish": "Commercial",
                    "ProjectArabic": "اليت بزنس باي ريذيدنس (منجز)",
                    "ProjectEnglish": "ELITE BUSINESS BAY RESIDENCE (FINISHED)",
                    "PropertyArabicDescription": "وحدة - ايليت بزنس باي ريذيدنس  - 1001",
                    "PropertyEnglishDescription": "Unit - Elite Business Bay Residence - 1001",
                    "PropertyID": 53237439,
                    "PropertyLocation": null,
                    "PropertySubTypeArabic": "شقه سكنيه",
                    "PropertySubTypeEnglish": "Flat",
                    "RoomsArabic": "استوديو",
                    "RoomsEnglish": "Studio",
                    "LandNo": "110",
                    "LandSubNo": "0",
                    "DMNo": "346",
                    "DMSubNo": "567",
                    "CanConvertToFreehold": false,
                    "AdditionalData": null,
                    "IsSuccess": true,
                    "ValidationErrors": []
                },
                "Id": 30583451,
                "Exception": null,
                "Status": 5,
                "IsCanceled": false,
                "IsCompleted": true,
                "IsCompletedSuccessfully": true,
                "CreationOptions": 0,
                "AsyncState": null,
                "IsFaulted": false
            },
            "propStatus": {
                "Result": {
                    "Area": 45.86,
                    "BlockingHistory": null,
                    "IsFreeHold": true,
                    "IsMortgaged": false,
                    "IsRegistered": true,
                    "IsRestrained": false,
                    "IsRestricted": false,
                    "LastTitleDeed": "325031/2024",
                    "MakaniNumber": "0",
                    "NumberOfOwners": 1,
                    "OwnerTypes": "PERSON",
                    "PreRegistrationNumber": null,
                    "PropertyId": 53237439,
                    "PropertyStatuses": [
                        {
                            "ArabicStatus": "ملك حر",
                            "EnglishStatus": "FREE",
                            "MortgageeName": null,
                            "StatusCode": "FREE"
                        }
                    ],
                    "RestrainList": null,
                    "TotalCount": 1,
                    "AdditionalData": null,
                    "IsSuccess": true,
                    "ValidationErrors": []
                },
                "Id": 30583733,
                "Exception": null,
                "Status": 5,
                "IsCanceled": false,
                "IsCompleted": true,
                "IsCompletedSuccessfully": true,
                "CreationOptions": 0,
                "AsyncState": null,
                "IsFaulted": false
            },
            "otherInfo": {
                "timeStamp": "2025-08-31T16:28:55.7019026+04:00",
                "responseCode": "Success",
                "validationErrorsList": [],
                "response": {
                    "items": [
                        {
                            "company": {
                                "identity": 94403,
                                "nameEn": "UNIVERSAL COMMUNITY MANAGEMENT L.L.C",
                                "nameAr": "يونيفرسال لادارة المجمعات ش.ذ.م.م",
                                "parentId": 0
                            },
                            "licenseNumber": "545530",
                            "licenseAuthorityId": 43,
                            "email": "mohamed@universaloam.com",
                            "phone": "+97144589027",
                            "mobile": "+971506568009",
                            "latitude": null,
                            "longitude": null,
                            "address": "P.O. Box No. 26125 Office No. Gg01, Hera Tower-Dubai Sport City"
                        }
                    ],
                    "additionalData": null
                }
            },
            "extraInfo": {
                "timeStamp": "2025-08-31T16:28:55.7330096+04:00",
                "responseCode": 200,
                "validationErrorsList": [],
                "response": {
                    "result": [
                        {
                            "PROPERTY_TYPE_ID": 2,
                            "PROPERTY_SUB_TYPE_ID": 2,
                            "PARCEL_ID": 3460567,
                            "LNG": 55.2657036,
                            "LAT": 25.17975427,
                            "IS_RENTED": null,
                            "DEWA_PREMISE": null
                        }
                    ],
                    "additionalData": null
                }
            },
            "metadata": {
                "cacheKey": "property_status_{\"buildingId\":53216779,\"unitNumber\":1001,\"serviceType\":\"PropStatusSearchByLand\"}_2025-08-31",
                "timestamp": 1756643337204,
                "steps": [
                    "captcha_token",
                    "prop_info",
                    "prop_status",
                    "other_info",
                    "extra_info"
                ]
            }
        },
        "serviceChargeResult": {
            "timeStamp": "2025-08-31T16:29:00.8583009+04:00",
            "responseCode": "Success",
            "validationErrorsList": [],
            "response": {
                "startDate": "2020-11-23T20:00:00",
                "endDate": "2020-12-31T20:00:00",
                "propertyManager": {
                    "identity": 94403,
                    "nameEn": "UNIVERSAL COMMUNITY MANAGEMENT L.L.C",
                    "nameAr": "يونيفرسال لادارة المجمعات ش.ذ.م.م",
                    "parentId": 0
                },
                "accountDetail": {
                    "bank": {
                        "englishName": "Abu Dhabi Commercial Bank P.J.S.C.",
                        "arabicName": "بنك أبوظبي التجاري"
                    },
                    "generalAccountTitle": "Elite Bus Bay Res GEN FUND ACC",
                    "generalIBAN": "AE560030011924407920001",
                    "reservedAccountTitle": "Elite Bus Bay Res RES FUND ACC",
                    "reservedIBAN": "AE290030011924407920002"
                },
                "serviceCharges": [
                    {
                        "categoryId": 1,
                        "categoryName": {
                            "englishName": "Services",
                            "arabicName": "خدمات"
                        },
                        "cost": 0.09,
                        "chargeTypeId": 1,
                        "chargeTypeName": {
                            "englishName": "General Fund",
                            "arabicName": "المبلغ العام"
                        },
                        "isFixedService": false
                    },
                    {
                        "categoryId": 5,
                        "categoryName": {
                            "englishName": "Utilities Services",
                            "arabicName": "المرافق"
                        },
                        "cost": 2.36,
                        "chargeTypeId": 1,
                        "chargeTypeName": {
                            "englishName": "General Fund",
                            "arabicName": "المبلغ العام"
                        },
                        "isFixedService": false
                    },
                    {
                        "categoryId": 7,
                        "categoryName": {
                            "englishName": "Insurance",
                            "arabicName": "تأمين"
                        },
                        "cost": 0.23,
                        "chargeTypeId": 1,
                        "chargeTypeName": {
                            "englishName": "General Fund",
                            "arabicName": "المبلغ العام"
                        },
                        "isFixedService": false
                    },
                    {
                        "categoryId": 12,
                        "categoryName": {
                            "englishName": "Reserved Fund",
                            "arabicName": "الصندوق الاحتياطي"
                        },
                        "cost": 1.04,
                        "chargeTypeId": 2,
                        "chargeTypeName": {
                            "englishName": "Reserved Fund",
                            "arabicName": "مبلغ الإحتياط"
                        },
                        "isFixedService": false
                    }
                ],
                "request": {
                    "areaId": 0,
                    "masterCommunityId": 0,
                    "projectId": 0,
                    "usageId": 1,
                    "year": 2020,
                    "propertyGroupId": 182020139,
                    "tabuPropertyId": 0,
                    "masterCommunityName": null,
                    "areaName": null,
                    "projectName": null,
                    "propertyGroupName": null,
                    "managementCompanyId": 0,
                    "managementCompanyName": null
                },
                "additionalData": null
            }
        },
        "errorMessage": null
    },
    "timestamp": "2025-08-31T12:29:00.811Z"
}
```

</details>
- Endpoint: `https://api.v2.keypilot.io/v1/property/titledeeds`
- Method: POST
- Description: Retrieve title deed information by certificate number and year, for a given property type.


Request body (JSON):
```json
{
	"propType": "unit",
	"certNumber": "121365",
	"certYear": "2023"
}
```

Original curl:
```bash
curl -X POST 'https://api.v2.keypilot.io/v1/property/titledeeds' \
	-H "Content-Type: application/json" \
	-d '{"propType":"unit","certNumber":"121365","certYear":"2023"}'
```

<details>
<summary>Response (example)</summary>

```json
{
    "status": "success",
    "message": "Property status by title deed fetched successfully",
    "responseStatus": 200,
    "result": {
        "projectDetails": null,
        "bigQueryResult": null,
        "propertyStatus": {
            "propInfo": {
                "Result": {
                    "DeveloperArabic": null,
                    "DeveloperEnglish": null,
                    "LandStatus": "PREMISED",
                    "LandTypeArabic": "تجارى",
                    "LandTypeEnglish": "Commercial",
                    "ProjectArabic": null,
                    "ProjectEnglish": null,
                    "PropertyArabicDescription": "وحدة - فيزول ريزيدنس - 1501",
                    "PropertyEnglishDescription": "Unit - Vezul Residence - 1501",
                    "PropertyID": 248239713,
                    "PropertyLocation": null,
                    "PropertySubTypeArabic": "شقه سكنيه",
                    "PropertySubTypeEnglish": "Flat",
                    "RoomsArabic": "غرفتان",
                    "RoomsEnglish": "2 B/R",
                    "LandNo": "100",
                    "LandSubNo": "0",
                    "DMNo": "346",
                    "DMSubNo": "147",
                    "CanConvertToFreehold": false,
                    "AdditionalData": null,
                    "IsSuccess": true,
                    "ValidationErrors": []
                },
                "Id": 11000,
                "Exception": null,
                "Status": 5,
                "IsCanceled": false,
                "IsCompleted": true,
                "IsCompletedSuccessfully": true,
                "CreationOptions": 0,
                "AsyncState": null,
                "IsFaulted": false
            },
            "propStatus": {
                "Result": {
                    "Area": 129.97,
                    "BlockingHistory": null,
                    "IsFreeHold": true,
                    "IsMortgaged": false,
                    "IsRegistered": true,
                    "IsRestrained": false,
                    "IsRestricted": false,
                    "LastTitleDeed": "121365/2023",
                    "MakaniNumber": "0",
                    "NumberOfOwners": 1,
                    "OwnerTypes": "PERSON",
                    "PreRegistrationNumber": null,
                    "PropertyId": 248239713,
                    "PropertyStatuses": [
                        {
                            "ArabicStatus": "ملك حر",
                            "EnglishStatus": "FREE",
                            "MortgageeName": null,
                            "StatusCode": "FREE"
                        }
                    ],
                    "RestrainList": null,
                    "TotalCount": 1,
                    "AdditionalData": null,
                    "IsSuccess": true,
                    "ValidationErrors": []
                },
                "Id": 11001,
                "Exception": null,
                "Status": 5,
                "IsCanceled": false,
                "IsCompleted": true,
                "IsCompletedSuccessfully": true,
                "CreationOptions": 0,
                "AsyncState": null,
                "IsFaulted": false
            },
            "otherInfo": {
                "timeStamp": "2025-08-31T16:34:23.6633424+04:00",
                "responseCode": "Success",
                "validationErrorsList": [],
                "response": {
                    "items": [
                        {
                            "company": {
                                "identity": 67861,
                                "nameEn": "PROVIS OWNERS ASSOCIATION MANAGEMENT SERVICES L.L.C",
                                "nameAr": "بروفيس لخدمات إدارة جمعيات الملاك ش.ذ.م.م",
                                "parentId": 0
                            },
                            "licenseNumber": "645568",
                            "licenseAuthorityId": 43,
                            "email": "j.hanna@asteco.com",
                            "phone": "+97142778182",
                            "mobile": "566068213",
                            "latitude": null,
                            "longitude": null,
                            "address": "3rd Floor, Rollex Tower, Sh.Zayed Rd. Dubai."
                        }
                    ],
                    "additionalData": null
                }
            },
            "extraInfo": {
                "timeStamp": "2025-08-31T16:34:23.69669+04:00",
                "responseCode": 200,
                "validationErrorsList": [],
                "response": {
                    "result": [
                        {
                            "PROPERTY_TYPE_ID": 3,
                            "PROPERTY_SUB_TYPE_ID": 60,
                            "PARCEL_ID": 3460147,
                            "LNG": 55.27746507,
                            "LAT": 25.17974092,
                            "IS_RENTED": 1,
                            "DEWA_PREMISE": "346096774"
                        }
                    ],
                    "additionalData": null
                }
            },
            "metadata": {
                "cacheKey": "property_status_{\"certNumber\":\"121365\",\"certYear\":\"2023\",\"serviceType\":\"SearchByTitleDeed\",\"propType\":3}_2025-08-31",
                "timestamp": 1756643664737,
                "steps": [
                    "captcha_token",
                    "prop_info",
                    "prop_status",
                    "other_info",
                    "extra_info"
                ]
            }
        },
        "serviceChargeResult": {
            "timeStamp": "2025-08-31T16:37:54.0187114+04:00",
            "responseCode": "Success",
            "validationErrorsList": [],
            "response": {
                "startDate": "2022-01-01T20:00:00",
                "endDate": "2022-12-31T20:00:00",
                "propertyManager": {
                    "identity": 67861,
                    "nameEn": "PROVIS OWNERS ASSOCIATION MANAGEMENT SERVICES L.L.C",
                    "nameAr": "بروفيس لخدمات إدارة جمعيات الملاك ش.ذ.م.م",
                    "parentId": 0
                },
                "accountDetail": {
                    "bank": {
                        "englishName": "Abu Dhabi Commercial Bank P.J.S.C.",
                        "arabicName": "بنك أبوظبي التجاري"
                    },
                    "generalAccountTitle": "VEZUL RESIDENCE GEN FUND ACC",
                    "generalIBAN": "AE090030012185142920001",
                    "reservedAccountTitle": "VEZUL RESIDENCE RES FUND ACC",
                    "reservedIBAN": "AE790030012185142920002"
                },
                "serviceCharges": [
                    {
                        "categoryId": 1,
                        "categoryName": {
                            "englishName": "Services",
                            "arabicName": "خدمات"
                        },
                        "cost": 0.65,
                        "chargeTypeId": 1,
                        "chargeTypeName": {
                            "englishName": "General Fund",
                            "arabicName": "المبلغ العام"
                        },
                        "isFixedService": false
                    },
                    {
                        "categoryId": 2,
                        "categoryName": {
                            "englishName": "Maintenance",
                            "arabicName": "صيانة"
                        },
                        "cost": 1.57,
                        "chargeTypeId": 1,
                        "chargeTypeName": {
                            "englishName": "General Fund",
                            "arabicName": "المبلغ العام"
                        },
                        "isFixedService": false
                    },
                    {
                        "categoryId": 5,
                        "categoryName": {
                            "englishName": "Utilities Services",
                            "arabicName": "المرافق"
                        },
                        "cost": 4.23,
                        "chargeTypeId": 1,
                        "chargeTypeName": {
                            "englishName": "General Fund",
                            "arabicName": "المبلغ العام"
                        },
                        "isFixedService": false
                    },
                    {
                        "categoryId": 6,
                        "categoryName": {
                            "englishName": "Management Services ",
                            "arabicName": "خدمات الإدارة"
                        },
                        "cost": 0.46,
                        "chargeTypeId": 1,
                        "chargeTypeName": {
                            "englishName": "General Fund",
                            "arabicName": "المبلغ العام"
                        },
                        "isFixedService": false
                    },
                    {
                        "categoryId": 7,
                        "categoryName": {
                            "englishName": "Insurance",
                            "arabicName": "تأمين"
                        },
                        "cost": 0.12,
                        "chargeTypeId": 1,
                        "chargeTypeName": {
                            "englishName": "General Fund",
                            "arabicName": "المبلغ العام"
                        },
                        "isFixedService": false
                    },
                    {
                        "categoryId": 8,
                        "categoryName": {
                            "englishName": "Master Community ",
                            "arabicName": "المجمع الرئيس"
                        },
                        "cost": 0.27,
                        "chargeTypeId": 1,
                        "chargeTypeName": {
                            "englishName": "General Fund",
                            "arabicName": "المبلغ العام"
                        },
                        "isFixedService": false
                    },
                    {
                        "categoryId": 12,
                        "categoryName": {
                            "englishName": "Reserved Fund",
                            "arabicName": "الصندوق الاحتياطي"
                        },
                        "cost": 0.71,
                        "chargeTypeId": 2,
                        "chargeTypeName": {
                            "englishName": "Reserved Fund",
                            "arabicName": "مبلغ الإحتياط"
                        },
                        "isFixedService": false
                    }
                ],
                "request": {
                    "areaId": 0,
                    "masterCommunityId": 0,
                    "projectId": 0,
                    "usageId": 6,
                    "year": 2022,
                    "propertyGroupId": 519057738,
                    "tabuPropertyId": 0,
                    "masterCommunityName": null,
                    "areaName": null,
                    "projectName": null,
                    "propertyGroupName": null,
                    "managementCompanyId": 0,
                    "managementCompanyName": null
                },
                "additionalData": null
            }
        },
        "errorMessage": [
            {},
            {}
        ]
    },
    "timestamp": "2025-08-31T12:37:53.946Z"
}
```

</details>

---

## 4) Makani lookup

- Endpoint: `https://api.v2.keypilot.io/v1/property/makani`
- Method: POST
- Description: Retrieve property info by Makani number.


Request body (JSON):
```json
{
	"makaniNumber": "2928496400"
}
```

Original curl:
```bash
curl -X POST 'https://api.v2.keypilot.io/v1/property/makani' \
	-H "Content-Type: application/json" \
	-d '{"makaniNumber":"2928496400"}'
```

<details>
<summary>Response (example)</summary>

```json
{
    "status": "success",
    "message": "Property status by Makani number fetched successfully",
    "responseStatus": 200,
    "result": {
        "projectDetails": {},
        "bigQueryResult": null,
        "propertyStatus": {
            "propInfo": {
                "Result": {
                    "DeveloperArabic": null,
                    "DeveloperEnglish": null,
                    "LandStatus": "PREMISED",
                    "LandTypeArabic": "تجارى",
                    "LandTypeEnglish": "Commercial",
                    "ProjectArabic": null,
                    "ProjectEnglish": null,
                    "PropertyArabicDescription": "ارض - تجارية - عيال ناصر - 208",
                    "PropertyEnglishDescription": "Land - Commercial - Eyal Nasser - 208",
                    "PropertyID": 52999,
                    "PropertyLocation": null,
                    "PropertySubTypeArabic": "تجارية",
                    "PropertySubTypeEnglish": "Commercial",
                    "RoomsArabic": null,
                    "RoomsEnglish": null,
                    "LandNo": "208",
                    "LandSubNo": "0",
                    "DMNo": "116",
                    "DMSubNo": "502",
                    "CanConvertToFreehold": false,
                    "AdditionalData": null,
                    "IsSuccess": true,
                    "ValidationErrors": []
                },
                "Id": 30536857,
                "Exception": null,
                "Status": 5,
                "IsCanceled": false,
                "IsCompleted": true,
                "IsCompletedSuccessfully": true,
                "CreationOptions": 0,
                "AsyncState": null,
                "IsFaulted": false
            },
            "propStatus": {
                "Result": {
                    "Area": 1332.7,
                    "BlockingHistory": null,
                    "IsFreeHold": false,
                    "IsMortgaged": false,
                    "IsRegistered": true,
                    "IsRestrained": false,
                    "IsRestricted": false,
                    "LastTitleDeed": "69795/2017",
                    "MakaniNumber": "0",
                    "NumberOfOwners": 1,
                    "OwnerTypes": "AUTHORITY",
                    "PreRegistrationNumber": null,
                    "PropertyId": 52999,
                    "PropertyStatuses": [
                        {
                            "ArabicStatus": "ملك حر",
                            "EnglishStatus": "FREE",
                            "MortgageeName": null,
                            "StatusCode": "FREE"
                        }
                    ],
                    "RestrainList": null,
                    "TotalCount": 1,
                    "AdditionalData": null,
                    "IsSuccess": true,
                    "ValidationErrors": []
                },
                "Id": 30537075,
                "Exception": null,
                "Status": 5,
                "IsCanceled": false,
                "IsCompleted": true,
                "IsCompletedSuccessfully": true,
                "CreationOptions": 0,
                "AsyncState": null,
                "IsFaulted": false
            },
            "otherInfo": {
                "timeStamp": "2025-08-31T16:27:03.2906816+04:00",
                "responseCode": "Empty",
                "validationErrorsList": [],
                "response": {
                    "items": null,
                    "additionalData": null
                }
            },
            "extraInfo": {
                "timeStamp": "2025-08-31T16:27:03.264688+04:00",
                "responseCode": 200,
                "validationErrorsList": [],
                "response": {
                    "result": [
                        {
                            "PROPERTY_TYPE_ID": 1,
                            "PROPERTY_SUB_TYPE_ID": 62,
                            "PARCEL_ID": 1160502,
                            "LNG": 55.30455448,
                            "LAT": 25.27446222,
                            "IS_RENTED": 0,
                            "DEWA_PREMISE": null
                        }
                    ],
                    "additionalData": null
                }
            },
            "metadata": {
                "cacheKey": "property_status_{\"makaniNumber\":\"2928496400\",\"serviceType\":\"SearchByMakani\"}_2025-08-31",
                "timestamp": 1756643224778,
                "steps": [
                    "captcha_token",
                    "prop_info",
                    "prop_status",
                    "other_info",
                    "extra_info"
                ]
            }
        },
        "serviceChargeResult": null,
        "errorMessage": [
            {},
            {}
        ]
    },
    "timestamp": "2025-08-31T12:27:10.736Z"
}
```

</details>

---

## 5) ConstList — list units by building name

- Endpoint: `https://api.v2.keypilot.io/v1/constList/list/units/db/AL MANARAH TOWER`
- Method: POST (example sends an empty data payload)
- Description: Returns units for the specified building/project. The example uses the building name as part of the path.


Original curl (empty body):
```bash
curl -X POST 'https://api.v2.keypilot.io/v1/constList/list/units/db/AL%20MANARAH%20TOWER'
```

<details>
<summary>Response (example)</summary>

```json
{
    "status": "success",
    "message": "Data fetched successfully",
    "responseStatus": 200,
    "result": [
        {
            "units": [
                "1001"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1002"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1003"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1004"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1005"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1006"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1007"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1008"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1009"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "101"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1010"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "102"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "103"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "104"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "105"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "106"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "107"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1101"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1102"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1103"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1104"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1105"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1106"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1107"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1108"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1109"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1110"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1201"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1202"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1203"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1204"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1205"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1206"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1207"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1208"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1209"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1210"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1301"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1302"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1303"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1304"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1305"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1306"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1307"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1308"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1309"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1310"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1401"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1402"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1403"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1404"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1405"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1406"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1407"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1408"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1409"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1410"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1501"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1502"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1503"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1504"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1505"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1506"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1507"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1508"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1509"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1510"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1601"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1602"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1603"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1604"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1605"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1606"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1607"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1608"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1609"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1610"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1701"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1702"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1703"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1704"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1705"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1706"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1707"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1708"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1709"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1710"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1801"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1802"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1803"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1804"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1805"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1806"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1807"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1808"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1809"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1810"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1901"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1902"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1903"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1904"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1905"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1906"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1907"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1908"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1909"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1910"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2001"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2002"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2003"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2004"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2005"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2006"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2007"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2008"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2009"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "201"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2010"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "202"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "203"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "204"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "205"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "206"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "207"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "208"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "209"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "210"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2101"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2102"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2103"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2104"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2105"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2106"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2107"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2108"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2109"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2110"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2201"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2202"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2203"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2204"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2205"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2206"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2207"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2208"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2209"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2210"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2301"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2302"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2303"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2304"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2305"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2306"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2307"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2308"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2309"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2310"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2401"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2402"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2403"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2404"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2405"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2406"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2407"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2408"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2409"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2410"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2501"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2502"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2503"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2504"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2505"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2506"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2507"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2508"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2509"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2510"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2601"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2602"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2603"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2604"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2605"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2606"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2607"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2608"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2609"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2610"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "301"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "302"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "303"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "304"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "305"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "306"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "307"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "308"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "309"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "310"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "401"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "402"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "403"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "404"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "405"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "406"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "407"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "408"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "409"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "410"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "501"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "502"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "503"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "504"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "505"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "506"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "507"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "508"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "509"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "510"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "601"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "602"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "603"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "604"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "605"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "606"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "607"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "608"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "609"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "610"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "701"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "702"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "703"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "704"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "705"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "706"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "707"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "708"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "709"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "710"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "801"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "802"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "803"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "804"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "805"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "806"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "807"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "808"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "809"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "810"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "901"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "902"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "903"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "904"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "905"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "906"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "907"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "908"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "909"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "910"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "RETAIL 1"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "RETAIL 2"
            ],
            "projectName": "AL MANARAH TOWER"
        }
    ],
    "timestamp": "2025-08-31T12:32:51.859Z"
}
```

</details>

Note: URL-encode spaces when calling from scripts or programs. If this endpoint is intended to be a GET, try removing `--data` and using GET instead.

---

## 6) ConstList — project list for query

- Endpoint: `https://api.v2.keypilot.io/v1/constList/ProjectList/Elite Business`
- Method: POST (example uses empty data)
- Description: Returns a list of projects matching the path segment.


Original curl:
```bash
curl 'https://api.v2.keypilot.io/v1/constList/ProjectList/Elite%20Business'
```

<details>
<summary>Response (example)</summary>

```json
{
    "status": "success",
    "message": "Project names fetched successfully",
    "responseStatus": 200,
    "result": [
        " DAMAC RIVERSIDE VIEWS - MARINE 4",
        " Mohammed Bin Rashid Al Maktoum City , District One Phase III  , Residences 22",
        " QASR SABAH I , II ,III ",
        " Qline (Qpoint phase II) R010",
        "014 TOWER",
        "1 Residences ",
        "10 OXFORD by IMAN ",
        "105 Residences by Kamdar",
        "11 Hills Park",
        "15 Northside",
        "161 Jumeirah Lane",
        "17 ICON BAY",
        "171 Garden Heights",
        "180 Degree",
        "1WOOD RESIDENCE ",
        "2020 Marquis",
        "23 MARINA",
        "29 BOULEVARD",
        "310 Riverside Crescent",
        "311 Boulevard by Bam Eskan",
        "320 Riverside Crescent",
        "340 Riverside Crescent",
        "350 Riverside Crescent",
        "360 Riverside Crescent",
        "399 Hills Park A",
        "399 Hills Park B",
        "48 PARKSIDE ",
        "4B Living",
        "51@BUSINESS BAY",
        "5242",
        "555 PARK VIEWS",
        "7 PARK CENTRAL BY METEORA",
        "99 PARK PLACE",
        "A 99",
        "AARK RESIDENCES",
        "AB CAVALIER ",
        "ABJAR TOWER",
        "AC3",
        "ACACIA AT PARK HEIGHTS",
        "ACES CHATEAU",
        "ACT ONE | ACT TWO",
        "ADDRESS HARBOUR POINT",
        "ADEBA AZIZI ",
        "AG 7EVEN",
        "AG 9INE",
        "AG ARK TOWER",
        "AG AUM RESIDENCE",
        "AG CENTRAL",
        "AG SQUARE",
        "AG TOWER",
        "AIRE DUBAI",
        "AJMAL SARAH",
        "AL Andalus Phase 2",
        "AL BAHIA",
        "AL DUAA RESIDENCE",
        "AL FAHAD 4",
        "AL FALAK RESIDENCE",
        "AL HABTOOR  ISLAND RESORT & SPA",
        "AL HABTOOR CITY",
        "AL HELAL AL ZAHABY  2",
        "AL HELAL AL ZAHABY 3",
        "AL HELAL AL ZAHABY BUILDING",
        "AL JAWHARA TOWER ",
        "AL JAWZAA",
        "AL KHAIL HEIGHTS",
        "AL MANARA",
        "AL MANARAH TOWER",
        "AL MAS TOWER",
        "AL QURASHI",
        "AL SEEF II",
        "AL SERH RESIDENCES 11 BY ASAK REAL ESTATE DEVELOPMENT",
        "AL WALEED GARDEN 2",
        "ALANDALUS",
        "ALANDALUS BUILDING E",
        "ALBA",
        "ALBA TOWER",
        "ALBERO BY ORO24",
        "ALCOVE",
        "ALEF NOON RESIDENCE",
        "ALFATTAN HOTEL & RESIDENSE",
        "ALMASAH TOWER",
        "ALSEEF I",
        "ALSHERA TOWER",
        "ALTAI TOWER",
        "ALTIA ONE",
        "ALTIA RESIDENCE",
        "ALandalus Building D",
        "AMAAL 8",
        "AMAL TOWER",
        "AMALIA RESIDENCES",
        "AMESCO TOWER",
        "AMETHYST BY SIROYA",
        "ANGELICA RESIDENCE 1",
        "APEX ATRIUM",
        "APEX SUITES",
        "AQUARIUS GATE TOWER",
        "ARABIAN GATE",
        "ARABIAN RANCHES - SAMARA COMMUNITY",
        "ARAS HEIGHTS",
        "ARAS Residence",
        "ARBOR VIEW",
        "ARCHERY TOWER",
        "ARENA APARTMENTS",
        "ARIA",
        "ARLO",
        "ARMADA TOWERS",
        "AROOJ PALACE",
        "ART BAY EAST",
        "ART BAY WEST",
        "ARTISTIC HEIGHTS",
        "ARYENE GREENS",
        "ASCOT RESIDENCES",
        "ASHAI TOWER 5",
        "ASTORIA RESIDNECE",
        "AU TOWER",
        "AURA ELEGANCE",
        "AURA ELITE",
        "AURA by Grovy",
        "AUROR RESIDENCE 2",
        "AURORA RESIDENCE 1",
        "AVA AT PALM JUMEIRAH BY OMNIYAT",
        "AVA DESIGNER RESEDENSS",
        "AVALON TOWER",
        "AVANOS",
        "AVANT GARDE RESIDENCES BY SKYLINE",
        "AVANTI TOWER",
        "AVENUE RESIDENCE 4",
        "AVENUE RESIDENCE 5",
        "AVENUE RESIDENCE 6",
        "AVENUE RESIDENCE Three",
        "AVENUE RESIDENCE1",
        "AXIS  RESIDENCES 1",
        "AXIS RESIDENCES 2",
        "AXIS RESIDENCES 20",
        "AXIS RESIDENCES 3",
        "AXIS RESIDENCES 4",
        "AXIS RESIDENCES 5",
        "AXIS RESIDENCES 6",
        "AXIS RESIDENCES 7",
        "AXIS RESIDENCES 8",
        "AXIS SILVER",
        "AYKON CITY ",
        "AYKON CITY 2",
        "AYKON CITY 3",
        "AZHA DOWNTOWN RESIDENCES",
        "AZIZI AMBER",
        "AZIZI JEWEL ",
        "AZIZI NEILA",
        "AZIZI RIVIERA 61",
        "AZIZI RIVIERA 63 ",
        "AZIZI RIVIERA 65",
        "AZIZI RIVIERA 67",
        "AZIZI RIVIERA 69",
        "AZIZI RIVIERA AZURE",
        "AZIZI VENICE 1 ",
        "AZIZI VENICE 10",
        "AZIZI VENICE 11",
        "AZIZI VENICE 14",
        "AZIZI VENICE 2",
        "AZIZI VENICE 3",
        "AZIZI VENICE 4",
        "AZIZI VENICE 5",
        "AZIZI VENICE 7",
        "AZIZI VENICE 8",
        "AZIZI VENICE 9 ",
        "AZIZI VISTA ",
        "AZIZI ZAIN ",
        "AZIZI. DAISY",
        "AZIZI. FEIROUZ",
        "AZIZI. FREESIA",
        "AZIZI. ORCHID",
        "AZIZI. TULIP",
        "AZIZI. YASAMINE",
        "AZURE RESIDENCE",
        "Aba Lux Living",
        "Address Residences Zabeel",
        "Address Residences l Dubai Creek Harbour",
        "Address Residences l Dubai Hills Estate",
        "Address The Bay",
        "Adhara Star",
        "Aeon",
        "Aeternitas Tower",
        "Ahad Residences",
        "Al Fouad",
        "Al Habtoor Tower",
        "Al Haseen Residence",
        "Al Jazi - Madinat Jumeriah Living ",
        "Alandalus Building G",
        "Alexis Tower",
        "Alfal Residences",
        "All Seasons Residence",
        "Allura Residences by Citi Developers",
        "Altus",
        "Amana Jewels",
        "Anwa Aria by Omniyat",
        "Arisha Terraces ",
        "Armani Beach Residences At Palm Jumeirah",
        "Asayel at Madinat Jumeirah Living",
        "Ashton Park Residences",
        "Ashton Park Residences The Second",
        "Aura Central ",
        "Aurion Residence",
        "Aveline Residences by Citi Developers",
        "Avelon Boulevard",
        "Avenue Park Towers",
        "Avenue Residence 2",
        "Avenue Residence 7 By Nabni",
        "Avonlea",
        "Ayana Gardens",
        "Azizi  Riviera 34  ",
        "Azizi Aliyah Residences",
        "Azizi Aura Residences",
        "Azizi Berton",
        "Azizi Central ",
        "Azizi Farishta Residence ",
        "Azizi Gardens",
        "Azizi Grand",
        "Azizi Greenfield",
        "Azizi Mina",
        "Azizi Mirage 1",
        "Azizi Park Avenue ",
        "Azizi Pearl",
        "Azizi Plaza Hotel Apartments",
        "Azizi Riviera 1",
        "Azizi Riviera 10",
        "Azizi Riviera 11",
        "Azizi Riviera 12",
        "Azizi Riviera 13",
        "Azizi Riviera 14",
        "Azizi Riviera 15",
        "Azizi Riviera 16",
        "Azizi Riviera 17",
        "Azizi Riviera 18",
        "Azizi Riviera 19",
        "Azizi Riviera 2",
        "Azizi Riviera 20",
        "Azizi Riviera 21",
        "Azizi Riviera 22",
        "Azizi Riviera 23",
        "Azizi Riviera 24",
        "Azizi Riviera 25",
        "Azizi Riviera 26",
        "Azizi Riviera 27",
        "Azizi Riviera 28",
        "Azizi Riviera 29",
        "Azizi Riviera 3",
        "Azizi Riviera 30",
        "Azizi Riviera 31",
        "Azizi Riviera 32",
        "Azizi Riviera 33",
        "Azizi Riviera 35",
        "Azizi Riviera 36",
        "Azizi Riviera 37",
        "Azizi Riviera 38",
        "Azizi Riviera 39",
        "Azizi Riviera 4",
        "Azizi Riviera 40",
        "Azizi Riviera 41",
        "Azizi Riviera 42",
        "Azizi Riviera 43",
        "Azizi Riviera 44",
        "Azizi Riviera 45",
        "Azizi Riviera 46",
        "Azizi Riviera 47",
        "Azizi Riviera 48",
        "Azizi Riviera 5",
        "Azizi Riviera 59 ",
        "Azizi Riviera 6",
        "Azizi Riviera 7",
        "Azizi Riviera 8",
        "Azizi Riviera 9",
        "Azizi Riviera Beachfront",
        "Azizi Riviera Reve",
        "Azizi Samia Residence",
        "Azizi Shaista Residence",
        "Azizi Star Hotel Apartments",
        "Azizi. Iris",
        "Azizi. Liatris",
        "Azura Residences ",
        "B2B TOWER",
        "BADRA PHASE 1",
        "BAHWAN RESIDENCE ",
        "BAHWAN TOWER ",
        "BALQIS RESIDENCE",
        "BANYAN TREE RESIDENCES HILLSIDE DUBAI",
        "BAY CENTRAL WEST & CENTRAL TOWERS",
        "BAY SQUARE",
        "BAY'S EDGE",
        "BAYSIDE RESIDENCE",
        "BAYSWATER",
        "BAYVIEW",
        "BD BOULEVARD PLAZA",
        "BEACH ISLE",
        "BEACH OASIS 2",
        "BEACH VISTA",
        "BEACH WALK RESIDENCES 1",
        "BEACH WALK RESIDENCES 3 BY IMTIAZ",
        "BELGRAVIA",
        "BELGRAVIA HEIGHTS I",
        "BELGRAVIA HEIGHTS II",
        "BELGRAVIA III",
        "BELGRAVIA SQUARE",
        "BELLA ROSE",
        "BELLEVUE TOWERS",
        "BELMONT RESIDENCES ",
        "BERKELEY PLACE ",
        "BERLIN BUSINESS TOWER",
        "BERLIN CITY CENTER",
        "BERLIN CLASSIC 1",
        "BERLIN CLASSIC 2",
        "BERMUDA VIEWS",
        "BEVERLY BOULEVARD",
        "BEVERLY GARDENS BY AA AND HMB REAL ESTATE DEVELOPMENT",
        "BINGHATTI APARTMENTS",
        "BINGHATTI STARS",
        "BINGHATTI VIEWS",
        "BLISS HOMES",
        "BLOOM HEIGHTS",
        "BLUE MOON TOWER",
        "BLUE SKY",
        "BLUE WAVE",
        "BLVD CRESCENT ",
        "BLVD HEIGHTS",
        "BONNINGTON TOWER HOTEL & RESIDENCE DUBAI",
        "BOTANICA",
        "BRAND CENTRO",
        "BRIGHT CORNER",
        "BURJ AL NOOR",
        "BURJ AL NUJOOM",
        "BURJ AZIZI ",
        "BURJ DUBAI",
        "BURJ KHALIFA TOWERS",
        "BURJ PACIFIC",
        "BURJ PARK III",
        "BURJ PARK V",
        "BURJ VIEW RESIDENCE",
        "BURJ VIEWS",
        "BURJ VISTA",
        "BURLINGTON TOWER",
        "BUSINESS AVENUE AA1",
        "BUSINESS AVENUE BB1",
        "BUSINESS AVENUE BB2",
        "BUSINESS TOWER",
        "BV RESIDENCES",
        "Baccarat Hotel and Residences, Dubai",
        "Bali Residences",
        "Barari Parkview by Al Mawared",
        "Bay Grove Residences, Dubai Islands",
        "Bay Residences Dubai Islands",
        "Bayline",
        "Bayz 101 By Danube",
        "Bayz 102 By Danube ",
        "Bayz Tower",
        "Beach Mansion",
        "Beach Residences Dubai Islands",
        "Beach Walk Residences 2",
        "Beachgate by Address",
        "Belgravia 2",
        "Belle Reve By Zimaya",
        "Belvedere",
        "Berkshire Park",
        "Beverly Residence",
        "Beverly Residence 2",
        "Biltmore Sufouh",
        "Binghatti Amber",
        "Binghatti Apex",
        "Binghatti Aurora",
        "Binghatti Avenue",
        "Binghatti Azure",
        "Binghatti Canal",
        "Binghatti Corner",
        "Binghatti Creek",
        "Binghatti Crescent ",
        "Binghatti Crest",
        "Binghatti Elite",
        "Binghatti Emerald",
        "Binghatti Galaxy",
        "Binghatti Gardenia",
        "Binghatti Gate ",
        "Binghatti Gateway ",
        "Binghatti Gems",
        "Binghatti Ghost",
        "Binghatti Heights",
        "Binghatti Hills ",
        "Binghatti Hillviews",
        "Binghatti House",
        "Binghatti Ivory",
        "Binghatti Jasmine",
        "Binghatti Lavender ",
        "Binghatti Luna",
        "Binghatti Mirage",
        "Binghatti Nova",
        "Binghatti Onyx",
        "Binghatti Orchid",
        "Binghatti Phantom",
        "Binghatti Phoenix",
        "Binghatti Pinnacle",
        "Binghatti Point",
        "Binghatti Rose",
        "Binghatti Royale",
        "Binghatti Skyrise",
        "Binghatti Starlight",
        "Binghatti Tulip",
        "Binghatti Venus",
        "Bloom Towers",
        "Blossom 76 by Tranquil",
        "Bluewaters Bay ",
        "Bluewaters Residences ",
        "Bonds Avenue Residences",
        "Boulevard Point",
        "Boutique 23",
        "Boutique Xll",
        "Bugatti Residences by Binghatti",
        "Bulgari Lighthouse Dubai ",
        "Burj Binghatti Jacob & Co. Residences ",
        "Burj Crown",
        "Burj Royale",
        "Burj Sabah",
        "CAMBRIDGE",
        "CAMBRIDGE BUSINESS CENTRE",
        "CANADA BUSINESS CENTER",
        "CANAL CROWN",
        "CANAL CROWN 2",
        "CANAL HEIGHTS",
        "CANAL HEIGHTS 2",
        "CANAL RESIDENCE WEST (PHASE 1)",
        "CANDACE ACACIA HOTEL APARTMENTS",
        "CANDACE ASTER HOTEL APARTMENTS",
        "CAPITAL BAY  A",
        "CAPITAL BAY B",
        "CAPITAL SQUARE",
        "CAPPADOCIA",
        "CASA CANAL",
        "CASA FLORES AND EDEN APARTMENTS",
        "CASA VERONA",
        "CASSIA PARK",
        "CAVALLI CASA TOWER",
        "CAVALLI COUTURE",
        "CAYAN TOWER",
        "CELESTIA",
        "CELESTIAL HEIGHTS CAPELLA",
        "CELESTIAL HEIGHTS ORION",
        "CELESTIAL HEIGHTS POLARIS",
        "CELESTICA",
        "CELIA HEIGHTS",
        "CELIA RESIDENCE",
        "CENTER COURT",
        "CENTRAL SQUARE A & B",
        "CENTRIUM TOWER",
        "CENTURION RESIDENCE",
        "CHAIMAA PREMIERE",
        "CHAMPION TOWER 3",
        "CHAMPIONS TOWER1",
        "CHAMPIONS TOWER2",
        "CHAPAL EMIRATES POINT",
        "CHIC TOWER",
        "CHURCHILL TOWER",
        "CITADEL TOWER",
        "CITY APARTMENTS",
        "CLAREN 1",
        "CLAREN 2",
        "CLASSIC APARTMENTS",
        "CLAYDON HOUSE BY ELLINGTON ",
        "CLAYTON RESIDENCY",
        "CLOUD Tower ",
        "CLOVER BAY",
        "CLUB VILLAS",
        "CLUB VISTA MARE",
        "CONCEPT 7 RESIDENCES ",
        "CONCORDE TOWER",
        "CORAL INTERNATIONAL HOTEL APARTMENT",
        "CORAL REEF",
        "CORAL RESIDENCE",
        "CORDOBA PALACE",
        "CORPORATE BAY",
        "CREEK CRESCENT",
        "CREEK EDGE",
        "CREEK HEIGHTS",
        "CREEK HORIZON",
        "CREEK RISE ",
        "CREEK VIEWS",
        "CREEKSIDE 18",
        "CRICKET TOWER",
        "CRYSTAL RESIDENCE",
        "CRYSTAL TOWER",
        "California 2 by SD",
        "California by SD ",
        "Canal Front Residences CF1 & CF2",
        "Canal Front Residences-CF3&CF4",
        "Canal Front Residences-CF5&CF6",
        "Canal Front Residences-CF7 & CF8 & CF9",
        "Canal Residence West 2",
        "Casa Vista Residence By Golden Woods",
        "Castleton ",
        "Catch Residences By IGO ",
        "Cavendish Square",
        "Celadon ",
        "Celine By Vision",
        "Cello Residences",
        "Central Park Plaza",
        "Central Park at City Walk -Building 1",
        "Century",
        "Chaimaa Avenue",
        "Chaimaa Avenue 2",
        "Ciel",
        "Cilia",
        "City Center Residences",
        "City View Dubai Hills Residences",
        "City Walk Northline 1 ",
        "City Walk Northline 2",
        "Clearpoint",
        "Club Drive",
        "Club Place",
        "Collective",
        "Collective 2.0",
        "Como Residences",
        "Confident Lancaster",
        "Continental Tower",
        "Coral by Vision",
        "Cove Edition Residence 1 By Imtiaz",
        "Cove Edition Residence 2 By Imtiaz",
        "Cove Living Residence By Imtiaz",
        "Creek Beach - Bayshore",
        "Creek Beach - Breeze",
        "Creek Beach - Canopy - Moor",
        "Creek Beach - Grove",
        "Creek Beach - Lotus",
        "Creek Beach - Orchid",
        "Creek Beach - Rosewater",
        "Creek Beach - Savanna-Cedar-Mangrove",
        "Creek Beach - Summer",
        "Creek Beach - Sunset",
        "Creek Beach - Surf",
        "Creek Beach - VIDA Residences",
        "Creek Gate",
        "Creek Palace",
        "Creek Waters",
        "Creek Waters 2",
        "Cresswell Homes",
        "Cresswell Residences",
        "Cubix Residences",
        "D1",
        "DAMAC BAY",
        "DAMAC BAY 2",
        "DAMAC CASA",
        "DAMAC CITY",
        "DAMAC CITY 2",
        "DAMAC HEIGHTS",
        "DAMAC HILLS (2) - AVENCIA ",
        "DAMAC HILLS (2) - ELO",
        "DAMAC HILLS (2) - ELO 2 & ELO 3",
        "DAMAC HILLS (2) - EVERGREENS",
        "DAMAC HILLS (2) - NAVITAS ",
        "DAMAC HILLS (2) - NAVITAS (A & B) ",
        "DAMAC HILLS (2) - VIRIDIS ",
        "DAMAC HILLS - ARTESIA",
        "DAMAC HILLS - CARSON ",
        "DAMAC HILLS - GOLF GATE",
        "DAMAC HILLS - GOLF GATE 2",
        "DAMAC HILLS - GOLF GREENS 1",
        "DAMAC HILLS - GOLF GREENS 2",
        "DAMAC HILLS - GOLF HORIZON ",
        "DAMAC HILLS - GOLF PANORAMA",
        "DAMAC HILLS - GOLF PROMENADE",
        "DAMAC HILLS - GOLF TERRACE",
        "DAMAC HILLS - GOLF VEDUTA ",
        "DAMAC HILLS - GOLF VISTA",
        "DAMAC HILLS - GOLF VITA",
        "DAMAC HILLS - JASMINE",
        "DAMAC HILLS - LORETO",
        "DAMAC HILLS - ORCHID",
        "DAMAC LAGOONS - LAGOON VIEWS 1",
        "DAMAC LAGOONS - LAGOON VIEWS 10",
        "DAMAC LAGOONS - LAGOON VIEWS 11",
        "DAMAC LAGOONS - LAGOON VIEWS 12",
        "DAMAC LAGOONS - LAGOON VIEWS 13",
        "DAMAC LAGOONS - LAGOON VIEWS 14",
        "DAMAC LAGOONS - LAGOON VIEWS 2",
        "DAMAC LAGOONS - LAGOON VIEWS 3",
        "DAMAC LAGOONS - LAGOON VIEWS 4",
        "DAMAC LAGOONS - LAGOON VIEWS 5",
        "DAMAC LAGOONS - LAGOON VIEWS 6",
        "DAMAC LAGOONS - LAGOON VIEWS 7",
        "DAMAC LAGOONS - LAGOON VIEWS 8",
        "DAMAC LAGOONS - LAGOON VIEWS 9",
        "DAMAC RIVERSIDE VIEWS - MARINE 1 ",
        "DAMAC RIVERSIDE VIEWS - MARINE 2",
        "DAMAC RIVERSIDE VIEWS - MARINE 3",
        "DAMAC TOWERS BY PARAMOUNT",
        "DANA ROYALE TOWER 1",
        "DANA TOWER",
        "DAR AL JAWHARA",
        "DAYTONA HOUSE",
        "DD BOULEVARD CENTRAL",
        "DD STAND POINT",
        "DEANSGATE by ADE",
        "DEFINE VISION",
        "DESERT ROSE",
        "DESERT SUN TOWER",
        "DESIGN QUARTER",
        "DETROIT HOUSE",
        "DEYAAR PARK",
        "DEZIRE RESIDENCES",
        "DG1 Living ",
        "DIAMOND ARCH1",
        "DIAMOND BUSINESS CENTER",
        "DIAMOND VIEWS 1",
        "DIAMOND VIEWS 2",
        "DIAMOND VIEWS 3",
        "DIAMOND VIEWS 4",
        "DM MARINA PLAZA",
        "DOLCE VITA",
        "DOWNTOWN VIEWS",
        "DRAGON VIEW",
        "DREAM HARBOUR",
        "DREAM SQUARE",
        "DT 1",
        "DUBAI ARCH TOWER",
        "DUBAI LAGOON I SUITES HOTEL APARTMENT",
        "DUBAI LAGOON I SUITES SMART RESIDENCE",
        "DUBAI LAGOON LILY",
        "DUBAI LAGOON LOTUS",
        "DUBAI LAGOON ROWAN",
        "DUBAI LAGOON WINTERBERRY",
        "DUBAI MARINA",
        "DUBAI MARINA MALL",
        "DUBAI PEARL",
        "DUBAI STAR",
        "DUBAI WATER FRONT BADRAH",
        "DUBAI WHARF",
        "DUNES LILAC",
        "DUNES MARIGOLD",
        "DUNES RESIDENCE",
        "DUNES VILLAGE",
        "DURAR1",
        "DUSIT EMIRATES SARAY",
        "Dawn by Binghatti",
        "Diamondz By Danube ",
        "Divine Living",
        "Divine Residencia",
        "Dolphin Tower",
        "Dorchester Collection Dubai",
        "Downtown Views II",
        "Dubai Harbour Residences (Area 1)",
        "Dubai Harbour Residences (Area 3)",
        "Dubai Wharf - Tower 1",
        "Dubai Wharf - Tower 2",
        "Dune Residency Dubai",
        "Dusit Princess Rijas",
        "Dusk by Binghatti",
        "EAGLE HEIGHTS",
        "EATON",
        "EATON PLACE",
        "ECLIPSE TOWER",
        "ECO FUSION TOWER",
        "EDEN 1",
        "EDEN 2",
        "EDEN GARDEN",
        "EDMONTON ELM",
        "ELANO BY ORO24",
        "ELARA",
        "ELASH",
        "ELBRUS TOWER",
        "ELEGANCE TOWER",
        "ELEGANT TOWER",
        "ELEVATE by Prescott",
        "ELEVE BY DEYAAR",
        "ELITE 10 SPORTS RESIDENCE",
        "ELITE 3 SPORTS RESIDENCE",
        "ELITE 4 SPORTS RESIDENCE",
        "ELITE 5 SPORTS RESIDENCE",
        "ELITE 6 SPORTS RESIDENCE",
        "ELITE 7 SPORTS RESIDENCE",
        "ELITE 8 SPORTS RESIDENCE",
        "ELITE 9 SPORTS RESIDENCE",
        "ELITE BUSINESS BAY RESIDENCE",
        "ELITE DOWNTOWN RESIDENCE",
        "ELITE II SPORTS RESIDENCE",
        "ELITE RESIDENCE",
        "ELITE SPORTS RESIDENCE",
        "ELLINGTON BEACH HOUSE",
        "ELLINGTON HOUSE ",
        "ELLINGTON HOUSE II",
        "ELLINGTON HOUSE III",
        "ELLINGTON HOUSE IV",
        "ELYSEE II by PANTHEON",
        "ELZ Residence",
        "EMERALD PALACE KEMPINSKI",
        "EMERALD PALACE KEMPINSKI HOTEL",
        "EMIRATES GARDEN 1 (LAVENDER - GARDENIA - ROSE)",
        "EMIRATES GARDEN 2 (MAPLE- MAGNOLA - MULBERRY)",
        "EMIRATES GARDEN I - GARDENIA",
        "EMIRATES GARDEN I - ROSE 1",
        "EMIRATES GARDEN II - MAGNOLIA",
        "EMIRATES GARDEN II - MAPLE ",
        "EMPIRE HEIGHTS",
        "ENI CORAL TOWER",
        "ENSO AMBER",
        "ENSO JADE",
        "EQUITI APARTMENTS",
        "EQUITI ARCADE",
        "EQUITI GATES",
        "EQUITI HOME",
        "EQUITI RESIDENCE ",
        "EQUITI TOWER",
        "ESCAN MARINA TOWER",
        "EVERGRIN HOUSE",
        "EXECUTIVE BAY B",
        "EXECUTIVE HEIGHT",
        "EXQUISITE LIVING RESIDENCES",
        "EYWA DUBAI",
        "Easy18",
        "Eden House The Canal",
        "Eden House The Park",
        "Edgewater Residences",
        "Edgewater Residences 2",
        "Edison House",
        "Elaya",
        "Electra",
        "Elegance by Chaimaa Holding",
        "Elitz 2 By Danube",
        "Elitz 3 By Danube ",
        "Elitz By Danube ",
        "Elvira",
        "Elysee Heights",
        "Elysee III by Pantheon",
        "Emerald Vision Tower ",
        "Empire Estates ",
        "Empire Livings",
        "Empire Residence",
        "Enara By Omniyat",
        "Enaya Residences",
        "Enqlave By Aqasa",
        "Erin",
        "Euphoric Residences",
        "Evora Residences",
        "Exotica by Al Marina",
        "Expo City Mangrove Residences",
        "Expo City Sidr Residences",
        "Expo City Sky Residences",
        "FAHAD 2",
        "FAIR VIEW RESIDENCY",
        "FAIRMONT PALM HOTEL & RESORT",
        "FAIRMONT PALM RESIDENCE",
        "FAIRWAY HEIGHTS - SUNNINGDALE & WENTWOETH (B)",
        "FAY",
        "FERRETTI LUXURY BEACH RESDIENCE TWIN TOWER",
        "FH Residency",
        "FIA",
        "FIORELLA RESIDENCES",
        "FIRST CENTRAL",
        "FIVE LUXE",
        "FLAMINGO COVE",
        "FOREST CITY TOWER",
        "FORTE",
        "FORTUNATO",
        "FORUM RESIDENCES",
        "FRANKFURT SPORTS TOWER I",
        "FRANKFURT TOWER",
        "Fairway Residences By Prescott",
        "Farhad Azizi Residence",
        "Fashionz 1 By Danube",
        "Fawad Azizi Residence",
        "Fern",
        "Five at Jumeirah Village Circle Dubai",
        "Floarea Residence",
        "Floarea Vista",
        "Franck muller Vanguard ",
        "GALLERY VILLAS",
        "GARDEN HEIGHTS",
        "GARDENIA1 & 2",
        "GARDENS 2",
        "GATEWAY BY PREMIER CHOICE",
        "GEMINI SPLENDOR",
        "GEMZ by Danube ",
        "GENESIS",
        "GERMAN DESIGN TOWER 1",
        "GERMAN SPORTS TOWER2",
        "GERMAN SUPREME TOWER 2",
        "GHAFF LAND RESIDENCE",
        "GHALIA",
        "GHARBI II RESIDENCES",
        "GIOVANNI BOUTIQUE",
        "GLAMZ RESIDENCE",
        "GLITZ RESIDENCE 1",
        "GLITZ RESIDENCE 2",
        "GLITZ RESIDENCE 3",
        "GLOBAL GOLF RESIDENCE 2",
        "GLOBAL GREEN VIEW II",
        "GLOBAL LAKE VIEW",
        "GLOBAL POINT",
        "GLOBAL ROYAL TOWER",
        "GOLD CREST EXECUTIVE",
        "GOLD CREST VIEWS2",
        "GOLDEN MILE",
        "GOLF TOWER",
        "GOLF VIEW RESIDENCE",
        "GORDION",
        "GRAND CENTRAL",
        "GRAND HORIZON 1",
        "GRANDEUR RESIDENCES",
        "GREEN COMMUNITY  WEST-  EXTENSION- PHASE III",
        "GREEN DIAMOND 1",
        "GREEN PARK",
        "Gardenia Livings",
        "Gharbi I Residences",
        "Glorious Central Residences",
        "Golden Wood Views",
        "Golden Wood Views -1",
        "Golden Wood Views 5",
        "Golf Edge",
        "Golf Grand",
        "Golf Heights",
        "Golf Hillside",
        "Golf Point",
        "Golf Residences by Fortimo",
        "Golf Suites - Dubai Hills",
        "Golf Views ",
        "Golf Vista Heights",
        "Golf ville",
        "Grand Bleu Tower interiors by Elie Saab",
        "Grande",
        "Greenside Residence",
        "Grenland Residence By arloid",
        "Grove ",
        "H Three By Aurora",
        "HAMENI",
        "HAMILTON HOUSE",
        "HAMILTON RESIDENCY",
        "HAMPSTEAD RESIDENCES",
        "HAMZA TOWER",
        "HANOVER SQUARE",
        "HARBOUR LIGHTS",
        "HARBOUR RESIDENCES",
        "HARBOUR VIEWS",
        "HARRINGTON HOUSE",
        "HATIMI RESIDENCES BY FAKHRUDDIN",
        "HAVELOCK RESIDENCES",
        "HAVEN LIVING",
        "HAYAT BOULEVARD",
        "HDS BUSINESS CENTRE",
        "HDS SUNSTAR 1",
        "HELVETIA RESIDENCES",
        "HILIANA",
        "HILLMONT RESIDENCES BY ELLINGTON",
        "HOCKEY TOWER",
        "HOLLAND GARDENS ",
        "HORIZON1",
        "HORIZON2",
        "HUB CANAL 1 TOWER",
        "HUB CANAL 2 TOWER",
        "HYATI RESIDENCE",
        "HZ RESIDENCES 4",
        "Hadley Heights",
        "Hammock Park",
        "Harbour Gate ",
        "Havelock Heights",
        "Haven Bay Residences",
        "Haya on the Park",
        "Hera Tower",
        "Hillcrest",
        "Hills Park",
        "Hillside Residences 1",
        "Hillside Residences 2",
        "Hillside Residences 3",
        "Hyati Avenue",
        "Hyde Walk Residence by Imtiaz ",
        "I - RISE TOWER",
        "I-DUBAI",
        "ICON TOWER",
        "ICONIC",
        "IMAGE RESIDENCES",
        "IMPERIAL",
        "IMPERIAL RESIDENCE",
        "INDIGO CHAMBERS",
        "INDIGO OPTIMA 1",
        "INDIGO SPECTRUM 2",
        "INDIGO SPECTRUM1",
        "INDIGO TOWER",
        "INIGO ICON",
        "INTEGRAL 05",
        "INTERNATIONAL CITY EMARATI",
        "INTERNATIONAL CITY LAKE DISTRICT",
        "IRIS AMBER",
        "IRIS ASMAR",
        "IRIS BAY",
        "IT PLAZA",
        "Il PRIMO",
        "Iliyaa 5",
        "Iluka Residences",
        "Imperial  Avenue",
        "Imperial Residence",
        "Island Park I ",
        "Island Park II ",
        "J ONE",
        "J&G PLEXS",
        "J5",
        "J8",
        "JADE RESIDENCE",
        "JANNAT",
        "JASMINE GARDEN",
        "JOURI-4",
        "JOURI-5",
        "JOURI-6",
        "JOYA DORADO RESIDENCE",
        "JUMAA BUILDING",
        "JUMEIRAH BUSINESS CENTRE 4",
        "JUMEIRAH BUSINESS CENTRE 5",
        "JUMEIRAH BUSINESS CENTRE1",
        "JUMEIRAH BUSINESS CENTRE2",
        "JUMEIRAH BUSINESS CENTRE3",
        "JUMEIRAH GOLF ESTATES",
        "JUMEIRAH HEIGHTS CLUSTERS",
        "JUMEIRAH HEIGHTS FRONDS",
        "JUMEIRAH HILLS - THE PALACES",
        "JUMEIRAH LIVING MARINA GATE ",
        "JUMEIRAH PARK ",
        "JUMEIRAH PARK - PACKAGE 5A",
        "Jade Tower",
        "Jadeel -Madinat Jumeirah Living ",
        "Jardin Astral",
        "Jewelz Residence",
        "Jomana",
        "Joya Blanca Residences ",
        "Joya Mimosa Residences ",
        "Jumeirah Gate",
        "Jumeirah Living Business Bay ",
        "Jumeirah Living Marsa Al Arab",
        "K1",
        "KENSINGTON",
        "KENSINGTON KRYSTAL",
        "KENSINGTON ROYALE",
        "KENSINGTON WATERS",
        "KNIGHT BRIDGE COURT & KENSNGTON MANOR",
        "KPM 2 & 3",
        "KYOTO BY ORO24",
        "Kappa Acca 3",
        "Karma",
        "Kaya",
        "Kempinski Residences Business Bay",
        "Kempinski Residences The Creek",
        "Kenton Place",
        "Keturah Reserve",
        "Keturah Resort",
        "L'ORIENTAL",
        "LA FONTANA DI TREVI",
        "LA PERLA HOMES 12",
        "LA RESIDENZA",
        "LA RIVE",
        "LA RIVIERA AZURE",
        "LA RIVIERA ESTATE",
        "LA VISITA 01",
        "LA VISITA 02",
        "LA VISTA 03",
        "LA VISTA 04",
        "LA VISTA 05",
        "LA VISTA 06",
        "LA VISTA 07",
        "LADY RATAN MANOR",
        "LAGO VISTA",
        "LAGUNA TOWER",
        "LAKE CENTRAL",
        "LAKE CITY TOWER",
        "LAKE SHORE TOWER",
        "LAKE TERRACE",
        "LAKE VIEW",
        "LAKESIDE",
        "LAKESIDE RESIDENCE",
        "LAMER",
        "LATIFA TOWER",
        "LAWNSIV",
        "LAYA COURTYARD",
        "LAYA HEIGHTS",
        "LAZORD BY LAPIS",
        "LE GRAND CHATEAU",
        "LE PRESIDIUM",
        "LE STELLE1,2,3,4,5",
        "LEGACY BY SUNRISE",
        "LES VERTES",
        "LEVANTO BY ORO24",
        "LIBERTAS",
        "LILIUM TOWER",
        "LIME LIGHT TWIN TOWERS",
        "LINCOLN PARK",
        "LINCOLN PARK ( NORTH SIDE)",
        "LINCOLN PARK (MANHATTAN)",
        "LINCOLN PARK (SHEFFIELD)",
        "LINCOLN PARK(WEST SIDE & LINCOLN PARK - B)",
        "LIV LUX",
        "LIV MARINA",
        "LIV RESIDENCE",
        "LIVA",
        "LIVING LEGENDS PHASE 4",
        "LIVING LEGENDS PHASE 5",
        "LIVING LEGENDS PHASE 6",
        "LIVING LEGENDS PHASE 7",
        "LIWA HEIGHTS",
        "LOCI Residences",
        "LOLENA",
        "LUCE"
    ],
    "timestamp": "2025-10-04T20:49:56.638Z"
}
```

</details>

---

## 7) Similar properties (external API)

- Endpoint: `https://api.v2.keypilot.io/v1/similar/properties/Business Bay`
- Method: GET
- Description: Fetch similar properties for the given area (Business Bay) from Keypilot external API.


Original curl:
```bash
curl 'https://api.v2.keypilot.io/v1/similar/properties/Business%20Bay'
```

<details>
<summary>Response (example)</summary>

```json
{
    "result": {
        "results": [
            {
                "listingType": "property",
                "propertyId": "14689285",
                "reference": "PF-AS-140939",
                "title": "Modern Residence with Balcony in Prime Location",
                "description": "For Sale: 1-Bedroom Apartment in Aykon City, Business Bay, Dubai\n\nfäm Properties is pleased to present this brand-new, unfurnished 1-bedroom apartment located in the prestigious Aykon City development by Damac Properties, situated in the vibrant Business Bay district of Dubai.\n\nProperty Details:\n- Size: 683.29 sq.ft.\n- Price: AED 1,800,000\n- Bedrooms: 1\n- Bathrooms: 1\n- View: Community view\n- Floor: High floor\n\nKey Features and Amenities:\n- Built-in wardrobes\n- Spacious balcony\n- Modern open kitchen design\n- Air conditioning throughout\n- Elevator access\n- Located within a gated community\n- Access to shared swimming pools\n- Fully equipped fitness centre and gym\n- Brand new, contemporary design\n\nLocation Highlights:\nThis apartment enjoys a strategic location with easy access to major roads including Sheikh Mohammad Bin Zayed Road. It is in close proximity to iconic destinations such as Safa Park and Downtown Dubai, offering residents a balanced lifestyle of urban convenience and leisure.\n\nAbout fäm Properties:\nPresented by fäm Properties, Dubai’s largest and most trusted real estate agency, operating with over 700 agents across 24 locations. With a client satisfaction rating of 4.9 out of 5 stars and more than 9,200 happy clients, fäm Properties ensures a seamless and professional property transaction experience.\n\nFor further information or to arrange a viewing, please contact fäm Properties today.\n\nExperience luxury living in Business Bay with this exceptional opportunity at Aykon City.",
                "price": {
                    "value": 1800000,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "12588",
                    "name": "Safa Two",
                    "fullName": "Safa Two, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay",
                    "coordinates": {
                        "lat": 25.182546615600586,
                        "lon": 55.25239562988281
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/c86780592807dd03a707b2ae3397db2b/416/272/MODE/d53cca/14689285-454e1o.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/c86780592807dd03a707b2ae3397db2b/668/452/MODE/9e66d0/14689285-454e1o.jpg?ctr=ae"
                    },
                    {
                        "small": "https://www.propertyfinder.ae/property/b9688e6e4d5fdd8caddf581e3c4ba590/416/272/MODE/acb678/14689285-12d9eo.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/b9688e6e4d5fdd8caddf581e3c4ba590/668/452/MODE/cb8058/14689285-12d9eo.jpg?ctr=ae"
                    },
                    {
                        "small": "https://www.propertyfinder.ae/property/cc2b7ea8696050b99a5c0ca5700e0119/416/272/MODE/a2f04a/14689285-ca324o.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/cc2b7ea8696050b99a5c0ca5700e0119/668/452/MODE/e6bcc5/14689285-ca324o.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "290997",
                    "name": "Mohammad Jarrar",
                    "email": "mohammad.j@famproperties.com",
                    "phone": "+97143691700",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+PF-AS-140939%0AType%3A+Apartment%0APrice%3A+1%2C800%2C000+AED+%0ALocation%3A+Safa+Two+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F14689285%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English",
                        "Arabic"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/0bb5dbb0bb84c782fad7a5f3ceb13a4bda4fcd8b/desktop"
                },
                "broker": {
                    "id": "4196",
                    "name": "fam Properties - Branch 2",
                    "logo": "https://www.propertyfinder.ae/broker/4/178/98/MODE/1218ef/4196-logo.jpg?ctr=ae",
                    "address": "",
                    "email": "fateh@famproperties.com",
                    "phone": "+97143691700"
                },
                "details": {
                    "bedrooms": "1",
                    "bathrooms": "1",
                    "size": {
                        "value": 683,
                        "unit": "sqft"
                    },
                    "furnished": "NO",
                    "completionStatus": "completed",
                    "rera": "71441448800",
                    "offeringType": "Residential for Sale",
                    "amenities": [
                        "Balcony",
                        "Shared Pool",
                        "Built in Wardrobes",
                        "Shared Gym"
                    ]
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/apartment-for-sale-dubai-business-bay-safa-two-14689285.html",
                "listedDate": "2025-07-07T13:46:35Z",
                "isVerified": true,
                "isAvailable": true
            },
            {
                "listingType": "property",
                "propertyId": "14979609",
                "reference": "LRE-S-000449",
                "title": "Best in the market | Full Canal view | Vacant",
                "description": "Linda&#39;s Real Estate proudly present this Apartment in the pad Omniyat. \n\nProperty Features:\n\n- 1 Bedroom\n- Canal View\n- 1 Bathrooms\n- Unfurnished\n- Living Dining Area\n- Fully Fitted Kitchen\n- Built-in Wardrobes\n- Maintained very well  \n- BUA: 653 sq ft.\n- Vacant\n- 1 Parking\n\nCompany name: Linda&#39;s Real Estate\nRERA ORN: 24402\nAddress: Control Tower, 33rd Floor, Motor City, Dubai\nWebsite: www.lindas.ae\n\nCompany Profile: Named after Dubai’s real estate icon and our chairman Linda Mahoney,we stand on the shoulders of a giant who set the benchmark for great service in real estate 36 years ago. To this day, we carry on her vision and legacy. That means we know the neighbourhood’s coziest coffee spots, finest golf courses, quickest routes and shortcuts, and the best schools to send your little ones. Our goal?To help find your home where we live. Linda&#39;s, where home begins!",
                "price": {
                    "value": 1750000,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "2446",
                    "name": "The Pad",
                    "fullName": "The Pad, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay",
                    "coordinates": {
                        "lat": 25.184904098510742,
                        "lon": 55.2821044921875
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/711b5ec278fbad7ca84fac47aa1f777e/416/272/MODE/4aeb54/14979609-406afo.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/711b5ec278fbad7ca84fac47aa1f777e/668/452/MODE/130932/14979609-406afo.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "278405",
                    "name": "Sharen Wilson",
                    "email": "sharen.wilson@lindas.ae",
                    "phone": "+97144090962",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+LRE-S-000449%0AType%3A+Apartment%0APrice%3A+1%2C750%2C000+AED+%0ALocation%3A+The+Pad+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F14979609%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/2e2d042177255d647c24694d59f46cadb5249d8d/desktop"
                },
                "broker": {
                    "id": "4214",
                    "name": "Linda's Real Estate",
                    "logo": "https://www.propertyfinder.ae/broker/2/178/98/MODE/b14d82/4214-logo.jpg?ctr=ae",
                    "address": "Office 33rd floor, Building Control Tower, Motor City, Motor City., Dubai, ",
                    "email": "hello@lindas.ae",
                    "phone": "800546327"
                },
                "details": {
                    "bedrooms": "1",
                    "bathrooms": "1",
                    "size": {
                        "value": 653,
                        "unit": "sqft"
                    },
                    "furnished": "NO",
                    "completionStatus": "completed",
                    "rera": "7117947277",
                    "offeringType": "Residential for Sale",
                    "amenities": []
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/apartment-for-sale-dubai-business-bay-the-pad-14979609.html",
                "listedDate": "2025-08-18T08:25:11Z",
                "isVerified": true,
                "isAvailable": true
            },
            {
                "listingType": "property",
                "propertyId": "14978901",
                "reference": "PB-S-13374",
                "title": "Studio | Vacant on Transfer | Furnished",
                "description": "Arabian Estates is proud to present to you this Studio apartment in Aykon City Tower C , Business Bay.\n\n- Studio Apartment\n- 1 Bathroom\n- Vacant on Transfer,\n- 447.89 Approx Sq Ft.\n- Mid to High Floor\n- SZR Facing\n- 1 Parking Space\n- Aykon City Tower C\n\nApartment comprises; entrance with w/c and kitchenette complete with built in appliances, entrance hallway then opens on to the bright studio layout. Apartment is sold fully furnished, ready equipped for short term holiday rentals  or set for a long term tenant.\n\nAykon City Tower C sits on Sheikh Zayed Road overlooking the Dubai Water Canal, offering quick access to Downtown Dubai, Business Bay, DIFC, and Jumeirah. Its prime location places residents minutes from Safa Park, City Walk, and some of Dubai’s most vibrant lifestyle destinations.\n\nFor more information and viewing, please call\nLeon Wright | Senior Sales Broker\nRERA BRN| 41511\n\nArabian Estates is real estate agency based in Dubai. With a team of experienced and service minded agent ready to help clients buy, sell and rent their properties.",
                "price": {
                    "value": 995000,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "11980",
                    "name": "Aykon City Tower C",
                    "fullName": "Aykon City Tower C, Aykon City, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay, Aykon City",
                    "coordinates": {
                        "lat": 25.18020248413086,
                        "lon": 55.25243377685547
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/7f59884f1877557f492e7e609be81ecc/416/272/MODE/9ad7a3/14978901-53b82o.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/7f59884f1877557f492e7e609be81ecc/668/452/MODE/e8bfb6/14978901-53b82o.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "207010",
                    "name": "Leon Wright",
                    "email": "leon@arabianestates.ae",
                    "phone": "+971565221762",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+PB-S-13374%0AType%3A+Apartment%0APrice%3A+995%2C000+AED+%0ALocation%3A+Aykon+City+Tower+C+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F14978901%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/e3119cd0ccfe6ceb96831bf7212fe94670140bd0/desktop",
                    "social": "https://www.linkedin.com/in/leon-wright-29766284"
                },
                "broker": {
                    "id": "4464",
                    "name": "Arabian Estates",
                    "logo": "https://www.propertyfinder.ae/broker/9/178/98/MODE/4cd4e5/4464-logo.jpg?ctr=ae",
                    "address": "Office 11C-07, Building I-Rise Tower, Barsha Heights (Tecom), -, Dubai, ",
                    "email": "danial@arabianestates.ae",
                    "phone": "+971529519666"
                },
                "details": {
                    "bedrooms": "studio",
                    "bathrooms": "1",
                    "size": {
                        "value": 447,
                        "unit": "sqft"
                    },
                    "furnished": "YES",
                    "completionStatus": "completed",
                    "rera": "7129362373",
                    "offeringType": "Residential for Sale",
                    "amenities": [
                        "Balcony",
                        "Shared Pool",
                        "Shared Spa",
                        "Security",
                        "Covered Parking",
                        "Built in Wardrobes",
                        "Kitchen Appliances",
                        "Pets Allowed",
                        "Shared Gym"
                    ]
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/apartment-for-sale-dubai-business-bay-aykon-city-aykon-city-tower-c-14978901.html",
                "listedDate": "2025-08-18T07:39:27Z",
                "isVerified": true,
                "isAvailable": true
            },
            {
                "listingType": "property",
                "propertyId": "14770331",
                "reference": "AP37558",
                "title": "High Floor | Vacant | Large Layout",
                "description": "Property Features:\n\n• OMNIYAT\n• 1041 sq.ft.\n• 1 bedroom\n• 2 bathrooms\n• appliances included\n• luxury facilities \n• easy access \n• open kitchen\n• central location \n• popular residence\n• natural light\n• spacious\n\nFor sale in Opus Business Bay by OMNIYAT: a sophisticated and generously appointed 1‑bedroom, 2‑bathroom apartment offering approximately 1,041\u202fsq.ft. of luxury living in one of Dubai’s most iconic developments. The bright, airy layout features an open kitchen equipped with high‑end appliances, seamlessly flowing into the spacious living and dining area bathed in natural light. The master suite enjoys an en‑suite bathroom and generous proportions, while the second bathroom offers guest convenience or flexibility for visitors or office/study use. Residents enjoy OMNIYAT’s renowned world‑class luxury facilities, including spa, gym, pool, concierge, and beautifully curated communal spaces. Strategically positioned in a central location in Business Bay, this unit benefits from excellent connectivity and easy access to Sheikh Zayed Road, the Metro, Downtown Dubai attractions, and waterfront promenades. Set within a highly popular residence known for its architectural elegance and premium finishes, this apartment is perfect for discerning professionals or investors seeking a refined, move‑in‑ready property. Experience modern elegance, exceptional amenities, and a prime Business Bay address all wrapped into one sophisticated offering.\n\nReference Number AP37558",
                "price": {
                    "value": 3800000,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "2445",
                    "name": "The Opus",
                    "fullName": "The Opus, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay",
                    "coordinates": {
                        "lat": 25.18868064880371,
                        "lon": 55.26709747314453
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/052249449df6c38c1ff1907ead3f9986/416/272/MODE/cb02a2/14770331-ae0a6o.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/052249449df6c38c1ff1907ead3f9986/668/452/MODE/1a3c18/14770331-ae0a6o.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "281442",
                    "name": "Michaela Holesinska",
                    "email": "michaela.holesinska@savills.me",
                    "phone": "+971549942830",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+AP37558%0AType%3A+Apartment%0APrice%3A+3%2C800%2C000+AED+%0ALocation%3A+The+Opus+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F14770331%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English",
                        "Czech",
                        "Slovak"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/c48d5545c2d696799998256c1e6415a0669217ec/desktop"
                },
                "broker": {
                    "id": "149",
                    "name": "Savills Dubai",
                    "logo": "https://www.propertyfinder.ae/broker/8/178/98/MODE/aa55cf/149-logo.jpg?ctr=ae",
                    "address": "Office Level 15/14, Building Arenco Tower, Dubai Internet City, Sheikh Zayed Road, Dubai, PO Box 95246",
                    "email": "dubai@savills.me",
                    "phone": "+97143657700"
                },
                "details": {
                    "bedrooms": "1",
                    "bathrooms": "2",
                    "size": {
                        "value": 1041,
                        "unit": "sqft"
                    },
                    "furnished": "YES",
                    "completionStatus": "completed",
                    "rera": "7117422269",
                    "offeringType": "Residential for Sale",
                    "amenities": [
                        "Shared Spa",
                        "Security",
                        "Concierge",
                        "Built in Wardrobes",
                        "Kitchen Appliances",
                        "Shared Gym",
                        "Lobby in Building"
                    ]
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/apartment-for-sale-dubai-business-bay-the-opus-14770331.html",
                "listedDate": "2025-07-18T05:22:35Z",
                "isVerified": true,
                "isAvailable": true
            },
            {
                "listingType": "property",
                "propertyId": "14796818",
                "reference": "PB-S-8625-1",
                "title": "Spacious Studio | 6% ROI | Park Facing",
                "description": "Arabian Estates is proud to present to you this Studio apartment in Safeer Tower 1, Business Bay.\n\n- Studio Apartment\n- 1 Bathroom\n- Rented Until 31/10/2025 for AED 50,820 (6% NET ROI)\n- 461.99 Approx Sq Ft.\n- Lower  Floor\n- Pool and Park Facing\n- 1 Parking Space\n- Safeer Tower 1\n\nApartment comprises; entrance with w/c and built in wardrobes, entrance hallway then opens on to a semi open kitchen. The studio offers a good space that makes it possible to split in to a designated living space and bed space.\n\nSafeer Tower 1 is located close to the Business Bay exit to Al Khail Road. eveloped by Al Seeb Developers and Al Safeer Group, this mid-rise tower spans 18 floors and was completed in 2017\n\nFor more information and viewing, please call\nLeon Wright | Senior Sales Broker\nRERA BRN| 41511\n\nArabian Estates is real estate agency based in Dubai. With a team of experienced and service minded agent ready to help clients buy, sell and rent their properties.",
                "price": {
                    "value": 685000,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "2540",
                    "name": "Safeer Tower 1",
                    "fullName": "Safeer Tower 1, Safeer Towers, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay, Safeer Towers",
                    "coordinates": {
                        "lat": 25.177112579345703,
                        "lon": 55.27106475830078
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/ccb62481fb3015bc045fee52da18a541/416/272/MODE/85226e/14796818-15d71o.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/ccb62481fb3015bc045fee52da18a541/668/452/MODE/a69564/14796818-15d71o.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "207010",
                    "name": "Leon Wright",
                    "email": "leon@arabianestates.ae",
                    "phone": "+971565221762",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+PB-S-8625-1%0AType%3A+Apartment%0APrice%3A+685%2C000+AED+%0ALocation%3A+Safeer+Tower+1+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F14796818%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/e3119cd0ccfe6ceb96831bf7212fe94670140bd0/desktop",
                    "social": "https://www.linkedin.com/in/leon-wright-29766284"
                },
                "broker": {
                    "id": "4464",
                    "name": "Arabian Estates",
                    "logo": "https://www.propertyfinder.ae/broker/9/178/98/MODE/4cd4e5/4464-logo.jpg?ctr=ae",
                    "address": "Office 11C-07, Building I-Rise Tower, Barsha Heights (Tecom), -, Dubai, ",
                    "email": "danial@arabianestates.ae",
                    "phone": "+971529519666"
                },
                "details": {
                    "bedrooms": "studio",
                    "bathrooms": "1",
                    "size": {
                        "value": 461,
                        "unit": "sqft"
                    },
                    "furnished": "PARTLY",
                    "completionStatus": "completed",
                    "rera": "7117485451",
                    "offeringType": "Residential for Sale",
                    "amenities": [
                        "Central A/C",
                        "Balcony",
                        "Shared Pool",
                        "Security",
                        "Covered Parking",
                        "Built in Wardrobes",
                        "Shared Gym"
                    ]
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/apartment-for-sale-dubai-business-bay-safeer-towers-safeer-tower-1-14796818.html",
                "listedDate": "2025-07-22T08:26:28Z",
                "isVerified": true,
                "isAvailable": true
            },
            {
                "listingType": "project",
                "price": {},
                "location": {},
                "agent": {
                    "phone": null,
                    "whatsapp": null
                },
                "broker": {},
                "details": {}
            },
            {
                "listingType": "property",
                "propertyId": "14983557",
                "reference": "MPSP-12097",
                "title": "Pool View | Vacant Unit | Near Metro",
                "description": "Metropolitan Premium Properties is proud to present this elegant 1-bedroom apartment in Merano Tower, Business Bay.\n\nProperty Details and Features:\n1 Bedroom\nSize: 667 sq. ft.\nPool view\nVacant \nService charge: AED 19 per sq. ft.\nFully fitted open-plan kitchen\nSpacious living and dining area\nBasement parking\nTemperature-controlled swimming pool\nFully equipped modern gymnasium\nElegant lobby with 24/7 concierge\nHigh-speed elevators\nCovered secure parking\nWalking distance to metro station\nQuick access to main roads\n\nSet in the heart of Business Bay, Merano Tower offers a convenient lifestyle for professionals and couples. The area provides seamless connectivity to Downtown Dubai, shopping outlets, and a wide variety of restaurants.\n\nThe Metropolitan Group is the leading real estate agency in the UAE. We speak 44+ languages and offer our local and international clients exceptional service, expert advice, and comprehensive property sales, purchases, and rental support.",
                "price": {
                    "value": 1150000,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "549",
                    "name": "Merano Tower",
                    "fullName": "Merano Tower, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay",
                    "coordinates": {
                        "lat": 25.18488311767578,
                        "lon": 55.26056671142578
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/4f8ddd66ddc41f5e081f62ae61db95b2/416/272/MODE/22edb4/14983557-95f15o.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/4f8ddd66ddc41f5e081f62ae61db95b2/668/452/MODE/5ee29c/14983557-95f15o.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "248489",
                    "name": "Shakir Mustan",
                    "email": "shakir.chataiwala@mpd.ae",
                    "phone": "+971565054162",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+MPSP-12097%0AType%3A+Apartment%0APrice%3A+1%2C150%2C000+AED+%0ALocation%3A+Merano+Tower+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F14983557%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English",
                        "Hindi"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/a1b352125cb781e0d0dce000259868e7a13ea932/desktop",
                    "social": ""
                },
                "broker": {
                    "id": "918",
                    "name": "Metropolitan Premium Properties",
                    "logo": "https://www.propertyfinder.ae/broker/11/178/98/MODE/aab3fc/918-logo.jpg?ctr=ae",
                    "address": "Office Office 1806, Building Business Bay, Business Bay, AL MANARA TOWER, Dubai, PO Box 0",
                    "email": "gm@mpdubai.com",
                    "phone": "+971586488888"
                },
                "details": {
                    "bedrooms": "1",
                    "bathrooms": "2",
                    "size": {
                        "value": 668,
                        "unit": "sqft"
                    },
                    "furnished": "NO",
                    "completionStatus": "completed",
                    "rera": "7125282389",
                    "offeringType": "Residential for Sale",
                    "amenities": [
                        "Central A/C",
                        "Balcony",
                        "Shared Pool",
                        "Security",
                        "Covered Parking",
                        "Kitchen Appliances",
                        "Pets Allowed",
                        "Shared Gym"
                    ]
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/apartment-for-sale-dubai-business-bay-merano-tower-14983557.html",
                "listedDate": "2025-08-18T12:46:21Z",
                "isVerified": true,
                "isAvailable": true
            },
            {
                "listingType": "property",
                "propertyId": "14980210",
                "reference": "MPS-38641",
                "title": "Canal View | High Floor | Luxury | Brand New",
                "description": "Metropolitan Premium Properties is proud to present this brand-new 1-bedroom apartment in Peninsula Three, Business Bay. Located on a high floor, the unit offers stunning canal views, contemporary interiors, and a luxurious lifestyle in one of Dubai’s most sought-after districts.\n\nProperty details and features:\n\n1 Bedroom\nHigh floor with panoramic canal views\nSpacious living and dining area\nModern open-plan kitchen\nBuilt-in wardrobes\nBalcony\nAllocated parking space\nBrand-new, move-in ready\n\nPeninsula Three is part of the vibrant Business Bay waterfront community, offering world-class amenities including swimming pools, fitness centers, landscaped promenades, and retail outlets. With its prime location, residents enjoy easy access to Downtown Dubai, Dubai Mall, Burj Khalifa, and the city’s main business hubs, making it ideal for professionals and investors seeking both lifestyle and convenience.\n\nThe Metropolitan Group is the leading real estate agency in the UAE. We speak 44+ languages and offer our local and international clients exceptional service, expert advice, and comprehensive property sales, purchases, and rental support.",
                "price": {
                    "value": 1950000,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "11726",
                    "name": "Peninsula Three",
                    "fullName": "Peninsula Three, Peninsula, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay, Peninsula",
                    "coordinates": {
                        "lat": 25.184284210205078,
                        "lon": 55.26752471923828
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/4c34db2c6ebc91788c4d4740f02f2ba2/416/272/MODE/0ab40a/14980210-6a3ceo.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/4c34db2c6ebc91788c4d4740f02f2ba2/668/452/MODE/a12dcd/14980210-6a3ceo.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "248489",
                    "name": "Shakir Mustan",
                    "email": "shakir.chataiwala@mpd.ae",
                    "phone": "+971565054162",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+MPS-38641%0AType%3A+Apartment%0APrice%3A+1%2C950%2C000+AED+%0ALocation%3A+Peninsula+Three+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F14980210%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English",
                        "Hindi"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/a1b352125cb781e0d0dce000259868e7a13ea932/desktop",
                    "social": ""
                },
                "broker": {
                    "id": "918",
                    "name": "Metropolitan Premium Properties",
                    "logo": "https://www.propertyfinder.ae/broker/11/178/98/MODE/aab3fc/918-logo.jpg?ctr=ae",
                    "address": "Office Office 1806, Building Business Bay, Business Bay, AL MANARA TOWER, Dubai, PO Box 0",
                    "email": "gm@mpdubai.com",
                    "phone": "+971586488888"
                },
                "details": {
                    "bedrooms": "1",
                    "bathrooms": "1",
                    "size": {
                        "value": 669,
                        "unit": "sqft"
                    },
                    "furnished": "PARTLY",
                    "completionStatus": "off_plan",
                    "rera": "71406170939",
                    "offeringType": "Residential for Sale",
                    "amenities": [
                        "Study",
                        "Central A/C",
                        "Balcony",
                        "Private Jacuzzi",
                        "Security",
                        "Concierge",
                        "Covered Parking",
                        "Built in Wardrobes",
                        "Kitchen Appliances",
                        "View of Water",
                        "View of Landmark",
                        "Shared Gym",
                        "Barbecue Area"
                    ]
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/apartment-for-sale-dubai-business-bay-peninsula-peninsula-three-14980210.html",
                "listedDate": "2025-08-18T09:04:21Z",
                "isVerified": true,
                "isAvailable": true
            },
            {
                "listingType": "property",
                "propertyId": "15003806",
                "reference": "L-9431",
                "title": "Exclusive | Over 40th Floor | Best Layout",
                "description": "Equity is proud to present this 2-bedroom apartment in Paramount Tower D, Business Bay.\n\n- High Floor\n- Alcohol Bar in the Apartment\n- Perfect Condition\n- Vacant Now\n- 2 Bedrooms\n- 3 bathrooms\n- Unique Layout\n- 1,394.03 Sqft\n- Shared pool &amp; Gym\n- Brand New Furniture\n- Permit No.: \t7117449617\n\nParamount Tower D is the crown jewel of the development — the only tower with a poolside alcohol bar, making it the go-to spot for relaxed, resort-style vibes. Beyond the bar, residents enjoy exclusive access to designer lounges, high-end fitness facilities, and panoramic city views. With modern interiors, smart layouts, and a vibrant social atmosphere, Tower D offers a one-of-a-kind lifestyle you won’t find in any other tower.\n\nPlease be advised that all measurements and information are provided to the best of our knowledge. Equity disclaims any liability for inaccuracies or discrepancies.\n\nEquity\nRERA ORN: 43321\nAddress: Office 1902, Boulevard Plaza Tower 2, Downtown Dubai, Dubai, UAE",
                "price": {
                    "value": 2299999,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "2561",
                    "name": "Tower D",
                    "fullName": "Tower D, DAMAC Towers by Paramount, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay, DAMAC Towers by Paramount",
                    "coordinates": {
                        "lat": 25.185823440551758,
                        "lon": 55.29192352294922
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/a48f16614af991be0d6fd0a5cf8744b6/416/272/MODE/87ee9d/15003806-37d89o.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/a48f16614af991be0d6fd0a5cf8744b6/668/452/MODE/29d823/15003806-37d89o.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "286669",
                    "name": "Jordan Baker",
                    "email": "jordanbaker@equitydxb.com",
                    "phone": "+971565152433",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+L-9431%0AType%3A+Apartment%0APrice%3A+2%2C299%2C999+AED+%0ALocation%3A+Tower+D+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F15003806%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/6e4af6ebc0bb47a5399f2b4a08def2260c28f343/desktop"
                },
                "broker": {
                    "id": "9338",
                    "name": "EQUITY REAL ESTATES L.L.C",
                    "logo": "https://www.propertyfinder.ae/broker/4/178/98/MODE/c766a4/9338-logo.jpg?ctr=ae",
                    "address": "Office 1902, Building Boulevard Plaza Tower 2, Downtown Dubai, ., Dubai, ",
                    "email": "emrah@equitydxb.com",
                    "phone": "+971547177835"
                },
                "details": {
                    "bedrooms": "2",
                    "bathrooms": "3",
                    "size": {
                        "value": 1394,
                        "unit": "sqft"
                    },
                    "furnished": "YES",
                    "completionStatus": "completed",
                    "rera": "7117449617",
                    "offeringType": "Residential for Sale",
                    "amenities": []
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/apartment-for-sale-dubai-business-bay-damac-towers-by-paramount-tower-d-15003806.html",
                "listedDate": "2025-08-21T06:58:20Z",
                "isVerified": true,
                "isAvailable": true
            },
            {
                "listingType": "property",
                "propertyId": "14853132",
                "reference": "DPF-S-40105",
                "title": "Contemporary | Upgraded Interiors | Huge Terrace",
                "description": "\nBrought to you by Driven Properties, this 1 Bedroom Apartment is located in Bay Square Building 13, Bay Square, Business Bay.\n\nUnit Details:\n\n\n  * Vacant\n  * Mid Floor\n  * Unit Type: 1 Bedroom\n  * Boulevard and Burj Khalifa View\n  * Kitchen: Open and Fully Fitted\n  * Bathrooms: 2\n  * Built up Area: 1556.00 square feet\n  * No. of Parking: 1\n  * Furnished\n\nFeatures:\n\n\n  * Covered parking\n  * Built in wardrobes\n  * Lobby in Building\n  * Balcony\n  * Central air conditioning\n  * Kitchen Appliances\n  * Security\n  * View of Landmark\n\nBusiness Bay is a contemporary financial district packed with corporate high-rises, stylish\napartments buildings, and swanky hotels.\n\nAsk us about:\n\n\n  * Mortgage Advisory\n  * Property Management\n  * Holiday Homes\n  * Interior Design\n\nVisit our offices across Dubai&#39;s most popular communities including:\n\n\n  * Downtown Dubai\n  * Business Bay\n  * Dubai Creek Harbour\n  * Jumeirah Village Circle\n  * Dubai Hills Estate\n",
                "price": {
                    "value": 2350000,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "2486",
                    "name": "Bay Square Building 13",
                    "fullName": "Bay Square Building 13, Bay Square, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay, Bay Square",
                    "coordinates": {
                        "lat": 25.18619155883789,
                        "lon": 55.28132247924805
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/f19eb1213e2c8a569fa67438ec9e2a20/416/272/MODE/ab2652/14853132-b2dc4o.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/f19eb1213e2c8a569fa67438ec9e2a20/668/452/MODE/62a115/14853132-b2dc4o.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "128827",
                    "name": "Marcela Herrera",
                    "email": "marcela@drivenproperties.com",
                    "phone": "+971565037078",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+DPF-S-40105%0AType%3A+Apartment%0APrice%3A+2%2C350%2C000+AED+%0ALocation%3A+Bay+Square+Building+13+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F14853132%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/d32441482fd3e1ea142c5d5d07a6560eea7c3a49/desktop",
                    "social": "https://ae.linkedin.com/in/marcela-herrera-3976a9111"
                },
                "broker": {
                    "id": "948",
                    "name": "Driven Properties",
                    "logo": "https://www.propertyfinder.ae/broker/7/178/98/MODE/6b7674/948-logo.jpg?ctr=ae",
                    "address": "Office 101, Building Emaar Square - Building 3, Downtown Dubai, Sheikh Mohammed bin Rashid Blvd, Dubai, ",
                    "email": "abdullah@driven-properties.com",
                    "phone": "+97144297040"
                },
                "details": {
                    "bedrooms": "1",
                    "bathrooms": "2",
                    "size": {
                        "value": 1556,
                        "unit": "sqft"
                    },
                    "furnished": "YES",
                    "completionStatus": "completed",
                    "rera": "7128383300",
                    "offeringType": "Residential for Sale",
                    "amenities": []
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/apartment-for-sale-dubai-business-bay-bay-square-bay-square-building-13-14853132.html",
                "listedDate": "2025-07-30T11:01:01Z",
                "isVerified": true,
                "isAvailable": true
            },
            {
                "listingType": "property",
                "propertyId": "14804544",
                "reference": "BI-S-20-11724",
                "title": "URGENTLY FOR SALE | BEST PRICE | BEST VIEW",
                "description": "Safeer Tower 1: Your Luxurious Dubai Studio Awaits\n\nEmbrace sophisticated city living in this stunning studio apartment located in the prestigious Safeer Tower 1, Dubai.  Boasting 445 sqft of elegantly designed space, this property offers a perfect blend of comfort, convenience, and breathtaking views.  Step inside and be captivated by the seamless flow and high-quality finishes. This is more than just an apartment; it&#39;s a lifestyle upgrade.\n\nImagine waking up to the vibrant energy of Dubai, stepping onto your private balcony to enjoy the serene views of the parkland. This fully furnished studio is ready to welcome you home.\n\n**Property Features:**\n\n* Studio Apartment\n* 1 Bathroom\n* 444.98 sqft\n* Fully Fitted Kitchen\n* Built-in Wardrobes\n* Walk-in Closet\n* Marble Flooring\n* Balcony\n* Basement Parking\n* Intercom System\n\n**Building Amenities:**\n\n* 24-Hour Maintenance\n* Concierge Service\n* Covered Parking\n* Public Parking\n* Gymnasium\n* Swimming Pool\n* Private Swimming Pool (please verify availability)\n* Pets Allowed\n* Shops\n* Restaurants\n* Public Transport\n* View of Gardens\n* View of Parkland\n* Steam Room\n\n**Exceptional Location:**\n\nBenefit from an enviable location, close to everything Dubai has to offer.  Enjoy effortless access to:\n\n* Airport\n* Golf Course\n* Hospitals\n* Malls\n* Mosques\n* Schools\n* Supermarkets\n* Public Transportation\n* Numerous Restaurants\n\nThis is an exceptional opportunity to own a piece of Dubai’s vibrant lifestyle.  Don&#39;t miss out – schedule a viewing today!\n\nCompany name: Banke International Properties LLC\nRERA ORN: 12108\nAddress: 415 Emarat Atrium Building, Sheikh Zayed Road, Dubai, UAE \nPrimary email: enquiries@banke.ae\nWebsite: www.banke.ae\nCompany Profile: A real estate firm specializing in investment sales and leasing of both commercial and residential properties. We also offer property management services across Dubai.",
                "price": {
                    "value": 699000,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "2540",
                    "name": "Safeer Tower 1",
                    "fullName": "Safeer Tower 1, Safeer Towers, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay, Safeer Towers",
                    "coordinates": {
                        "lat": 25.177112579345703,
                        "lon": 55.27106475830078
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/50b6c22af3333d5304b413b31df8e954/416/272/MODE/72392a/14804544-a49cao.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/50b6c22af3333d5304b413b31df8e954/668/452/MODE/f66bf1/14804544-a49cao.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "255964",
                    "name": "Syed Shah",
                    "email": "syed.shah@banke.ae",
                    "phone": "+971565080191",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+BI-S-20-11724%0AType%3A+Apartment%0APrice%3A+699%2C000+AED+%0ALocation%3A+Safeer+Tower+1+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F14804544%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English",
                        "Urdu",
                        "Punjabi"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/064738f08a2129f54e0c3192e0f9be7802e7491a/desktop",
                    "social": ""
                },
                "broker": {
                    "id": "1438",
                    "name": "Banke International Properties",
                    "logo": "https://www.propertyfinder.ae/broker/16/178/98/MODE/f59adc/1438-logo.jpg?ctr=ae",
                    "address": "Office 430, Building Emarat Atrium Building, Al Wasl, SZR, Dubai, PO Box 75977",
                    "email": "accounts@banke.ae",
                    "phone": "+97143380088"
                },
                "details": {
                    "bedrooms": "studio",
                    "bathrooms": "1",
                    "size": {
                        "value": 445,
                        "unit": "sqft"
                    },
                    "furnished": "YES",
                    "completionStatus": "completed",
                    "rera": "7117485486",
                    "offeringType": "Residential for Sale",
                    "amenities": [
                        "Balcony",
                        "Private Pool",
                        "Shared Pool",
                        "Concierge",
                        "Covered Parking",
                        "Built in Wardrobes",
                        "Walk-in Closet",
                        "Kitchen Appliances",
                        "View of Landmark",
                        "Pets Allowed"
                    ]
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/apartment-for-sale-dubai-business-bay-safeer-towers-safeer-tower-1-14804544.html",
                "listedDate": "2025-07-23T07:22:31Z",
                "isVerified": true,
                "isAvailable": true
            },
            {
                "listingType": "project",
                "price": {},
                "location": {},
                "agent": {
                    "phone": null,
                    "whatsapp": null
                },
                "broker": {},
                "details": {}
            },
            {
                "listingType": "property",
                "propertyId": "14986521",
                "reference": "DPF-S-40412",
                "title": "Unique Layout | Fully Furnished | High Floor",
                "description": "\nBrought to you by Driven Properties, this 2 Bedroom Apartment is located in Amna, Business Bay.\nUnit Details:\n\n  * Vacant\n  * High floor\n  * View: Canal\n  * Kitchen: Open and Fully Fitted\n  * Bathrooms: 2\n  * Built up Area: 1511 square feet\n  * No. of Parking: 1\n  * Furnished: Yes\n\nFeatures:\n\n  * BBQ area\n  * Basement parking\n  * Balcony\n  * Central air conditioning\n  * Gymnasium\n  * Kitchen Appliances\n  * View of Landmark\n  * View of Water\n  * Shared swimming pool\n  * Pets allowed\n  * Walk-in Closet\n  * Childrens play area\n  * Concierge Service\n  * Metro station\n  * Dining in building\n  * Public parking\n  * Security\n  * Shops\n  * Restaurants\n  * Shopping mall\n  * Mosque\n  * Public transport\n\nBusiness Bay is a contemporary financial district packed with corporate high-rises, stylish apartments buildings, and swanky hotels.\nAsk us about:\n\n  * Mortgage Advisory\n  * Property Management\n  * Holiday Homes\n  * Interior Design\n\nVisit our offices across Dubai&#39;s most popular communities including:\n\n  * Business Bay\n  * Dubai Creek Harbour\n  * Jumeirah Village Circle\n  * Dubai Hills Estate\n",
                "price": {
                    "value": 3000000,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "8452",
                    "name": "Amna",
                    "fullName": "Amna, Al Habtoor City, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay, Al Habtoor City",
                    "coordinates": {
                        "lat": 25.183345794677734,
                        "lon": 55.256229400634766
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/0a4cc74d902bf39eaa7168d4d4e0df4a/416/272/MODE/e66908/14986521-ad0c2o.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/0a4cc74d902bf39eaa7168d4d4e0df4a/668/452/MODE/976365/14986521-ad0c2o.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "289491",
                    "name": "James Royle",
                    "email": "sales4@drivenproperties.com",
                    "phone": "+971545863054",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+DPF-S-40412%0AType%3A+Apartment%0APrice%3A+3%2C000%2C000+AED+%0ALocation%3A+Amna+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F14986521%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/e7f2d4f3dd8a90f85109885e3bc5cd3d0c0b36a0/desktop",
                    "social": "https://www.linkedin.com/in/jjroyle?"
                },
                "broker": {
                    "id": "948",
                    "name": "Driven Properties",
                    "logo": "https://www.propertyfinder.ae/broker/7/178/98/MODE/6b7674/948-logo.jpg?ctr=ae",
                    "address": "Office 101, Building Emaar Square - Building 3, Downtown Dubai, Sheikh Mohammed bin Rashid Blvd, Dubai, ",
                    "email": "abdullah@driven-properties.com",
                    "phone": "+97144297040"
                },
                "details": {
                    "bedrooms": "2",
                    "bathrooms": "2",
                    "size": {
                        "value": 1511,
                        "unit": "sqft"
                    },
                    "furnished": "YES",
                    "completionStatus": "completed",
                    "rera": "71361407768",
                    "offeringType": "Residential for Sale",
                    "amenities": []
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/apartment-for-sale-dubai-business-bay-al-habtoor-city-amna-14986521.html",
                "listedDate": "2025-08-19T06:00:49Z",
                "isVerified": true,
                "isAvailable": true
            },
            {
                "listingType": "property",
                "propertyId": "14932461",
                "reference": "L-9078",
                "title": "Fully Upgraded | Full Canal View | Vacant Now",
                "description": "Equity is delighted to present to you this stunningly upgraded1-bedroom apartment available for sale in Churchill Residential Towers, Business Bay, a perfect spot for a luxurious stay.\n\n- Fully Upgraded To A High Standard\n- Fully Furnished\n- 1 Bedroom\n- 1 Bathroom\n- 968 Sqft Approximately\n- 24/7 Security\n- Shared Pool and Gym Facilities\n- Full Canal Views\n- Prime Business Bay Location\n- Secure and Underground Parking\n- ENI Developer\n- Permit No.:\t7131187000\n\nFrom Churchill Residential Towers, it takes roughly 11 minutes to drive to Dubai Mall, 20 minutes to Palm Jumeirah, 19 minutes to Burj Al Arab, and 24 minutes to The Walk JBR. Dubai International Airport (DXB) is roughly an 18-minute drive, and the new Al Maktoum International Airport is roughly 41-minute drive.\n\nPlease be advised that all measurements and information are provided to the best of our knowledge. Equity disclaims any liability for inaccuracies or discrepancies.\n\nEquity\nRERA ORN: 43321\nAddress: Office 1902, Boulevard Plaza Tower 2, Downtown Dubai, Dubai, UAE",
                "price": {
                    "value": 1850000,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "2492",
                    "name": "Churchill Residency Tower",
                    "fullName": "Churchill Residency Tower, Churchill Towers, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay, Churchill Towers",
                    "coordinates": {
                        "lat": 25.181310653686523,
                        "lon": 55.262508392333984
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/239bac8333477a2f0fe380dd95469184/416/272/MODE/db6492/14932461-5e2bao.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/239bac8333477a2f0fe380dd95469184/668/452/MODE/ec6ea9/14932461-5e2bao.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "298295",
                    "name": "Kaviyan Mohamadi",
                    "email": "kaviyan@equitydxb.com",
                    "phone": "+971506410574",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+L-9078%0AType%3A+Apartment%0APrice%3A+1%2C850%2C000+AED+%0ALocation%3A+Churchill+Residency+Tower+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F14932461%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English",
                        "Kurdi"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/ef0068f01ca55b6825f05d9147782c272b0c1ebd/desktop"
                },
                "broker": {
                    "id": "9338",
                    "name": "EQUITY REAL ESTATES L.L.C",
                    "logo": "https://www.propertyfinder.ae/broker/4/178/98/MODE/c766a4/9338-logo.jpg?ctr=ae",
                    "address": "Office 1902, Building Boulevard Plaza Tower 2, Downtown Dubai, ., Dubai, ",
                    "email": "emrah@equitydxb.com",
                    "phone": "+971547177835"
                },
                "details": {
                    "bedrooms": "1",
                    "bathrooms": "1",
                    "size": {
                        "value": 968,
                        "unit": "sqft"
                    },
                    "furnished": "YES",
                    "completionStatus": "completed",
                    "rera": "7131187000",
                    "offeringType": "Residential for Sale",
                    "amenities": [
                        "Central A/C",
                        "Balcony",
                        "Shared Pool",
                        "Security",
                        "Concierge",
                        "Covered Parking",
                        "Built in Wardrobes",
                        "Kitchen Appliances",
                        "View of Water",
                        "View of Landmark",
                        "Pets Allowed",
                        "Shared Gym",
                        "Lobby in Building",
                        "Children's Play Area"
                    ]
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/apartment-for-sale-dubai-business-bay-churchill-towers-churchill-residency-tower-14932461.html",
                "listedDate": "2025-08-11T12:47:19Z",
                "isVerified": true,
                "isAvailable": true
            },
            {
                "listingType": "property",
                "propertyId": "14716156",
                "reference": "L-8363",
                "title": "Below Market Price | Best Location | 691.47 Sq Ft",
                "description": "Equity is delighted to present to you this stunning Studio Apartment available for sale in Bay Square 08, Business Bay by Dubai Properties.\n\n- Approximately 691.47 Sqft\n- Studio Apartment\n- Best Location\n- Ideal For Rental Investment &amp; Renovation Projects\n- Vacant\n- Dubai Properties Developer\n- Top Floor\n- Unfurnished\n- Cheapest Online\n- Below Market Price\n- Permit No.:\t7126903900\n\nFrom Bay Square 08, it takes roughly 4 minutes to drive to Dubai Mall, 25 minutes to Palm Jumeirah, 26 minutes to Burj Al Arab, and 29 minutes to The Walk JBR. Dubai International Airport (DXB) is roughly an 18-minute drive, and the new Al Maktoum International Airport is roughly a 41-minute drive.\n\nPlease be advised that all measurements and information are provided to the best of our knowledge. Equity disclaims any liability for inaccuracies or discrepancies.\n\nEquity.\nRERA ORN: 43321.\nAddress: Office 1902, Boulevard Plaza Tower 2, Downtown Dubai, Dubai, UAE.",
                "price": {
                    "value": 1100000,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "2481",
                    "name": "Bay Square Building 8",
                    "fullName": "Bay Square Building 8, Bay Square, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay, Bay Square",
                    "coordinates": {
                        "lat": 25.184825897216797,
                        "lon": 55.279640197753906
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/d4c274014d4837e9885cf350267767f4/416/272/MODE/d40d6d/14716156-184d8o.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/d4c274014d4837e9885cf350267767f4/668/452/MODE/5bb3e0/14716156-184d8o.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "298295",
                    "name": "Kaviyan Mohamadi",
                    "email": "kaviyan@equitydxb.com",
                    "phone": "+971506410574",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+L-8363%0AType%3A+Apartment%0APrice%3A+1%2C100%2C000+AED+%0ALocation%3A+Bay+Square+Building+8+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F14716156%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English",
                        "Kurdi"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/ef0068f01ca55b6825f05d9147782c272b0c1ebd/desktop"
                },
                "broker": {
                    "id": "9338",
                    "name": "EQUITY REAL ESTATES L.L.C",
                    "logo": "https://www.propertyfinder.ae/broker/4/178/98/MODE/c766a4/9338-logo.jpg?ctr=ae",
                    "address": "Office 1902, Building Boulevard Plaza Tower 2, Downtown Dubai, ., Dubai, ",
                    "email": "emrah@equitydxb.com",
                    "phone": "+971547177835"
                },
                "details": {
                    "bedrooms": "studio",
                    "bathrooms": "1",
                    "size": {
                        "value": 691,
                        "unit": "sqft"
                    },
                    "furnished": "NO",
                    "completionStatus": "completed",
                    "rera": "7126903900",
                    "offeringType": "Residential for Sale",
                    "amenities": [
                        "Central A/C",
                        "Balcony",
                        "Security",
                        "Concierge",
                        "Covered Parking",
                        "Built in Wardrobes",
                        "View of Landmark",
                        "Pets Allowed",
                        "Lobby in Building"
                    ]
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/apartment-for-sale-dubai-business-bay-bay-square-bay-square-building-8-14716156.html",
                "listedDate": "2025-07-10T13:11:33Z",
                "isVerified": true,
                "isAvailable": true
            },
            {
                "listingType": "property",
                "propertyId": "14984313",
                "reference": "DPF-S-40375",
                "title": "Brand New | Canal View | Vacant with Big Layout",
                "description": "\nBrought to you by Driven Properties, this 2 Bedroom Apartment is located in Urban Oasis, Business Bay.\n\nUnit Details:\n\n\n  * Vacant\n  * View: Canal\n  * Kitchen: Open and Fully Fitted\n  * Bathrooms: 3\n  * Built up Area: 1165 square feet\n  * No. of Parking: 2\n  * Unfurnished\n\nFeatures:\n\n\n  * Balcony\n  * BBQ area\n  * Built in wardrobes\n  * Gymnasium\n  * Upgraded interior\n  * Shared swimming pool\n  * View of Water\n  * Childrens play area\n  * Restaurants\n  * Shops\n  * Security\n\nBusiness Bay is a contemporary financial district packed with corporate high-rises, stylish apartments buildings, and swanky hotels.\n\n\nAsk us about:\n\n\n  * Mortgage Advisory\n  * Property Management\n  * Holiday Homes\n  * Interior Design\n\nVisit our offices across Dubai&#39;s most popular communities including:\n\n\n  * Business Bay\n  * Dubai Creek Harbour\n  * Jumeirah Village Circle\n  * Dubai Hills Estate\n",
                "price": {
                    "value": 2300000,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "11418",
                    "name": "Urban Oasis",
                    "fullName": "Urban Oasis, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay",
                    "coordinates": {
                        "lat": 25.18434715270996,
                        "lon": 55.259220123291016
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/8f3a5674d8d1d308589341ee1cd98ff1/416/272/MODE/2ba303/14984313-cfbf5o.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/8f3a5674d8d1d308589341ee1cd98ff1/668/452/MODE/7e2af0/14984313-cfbf5o.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "244273",
                    "name": "Maheer Silk",
                    "email": "maher@drivenproperties.com",
                    "phone": "+971562191226",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+DPF-S-40375%0AType%3A+Apartment%0APrice%3A+2%2C300%2C000+AED+%0ALocation%3A+Urban+Oasis+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F14984313%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English",
                        "Arabic"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/b6c1610752d527852cc0cda3ae75757dc79a2d3b/desktop",
                    "social": "https://www.linkedin.com/in/maher-al-selk-706980a"
                },
                "broker": {
                    "id": "948",
                    "name": "Driven Properties",
                    "logo": "https://www.propertyfinder.ae/broker/7/178/98/MODE/6b7674/948-logo.jpg?ctr=ae",
                    "address": "Office 101, Building Emaar Square - Building 3, Downtown Dubai, Sheikh Mohammed bin Rashid Blvd, Dubai, ",
                    "email": "abdullah@driven-properties.com",
                    "phone": "+97144297040"
                },
                "details": {
                    "bedrooms": "2",
                    "bathrooms": "3",
                    "size": {
                        "value": 1165,
                        "unit": "sqft"
                    },
                    "furnished": "NO",
                    "completionStatus": "completed",
                    "rera": "71151310017",
                    "offeringType": "Residential for Sale",
                    "amenities": []
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/apartment-for-sale-dubai-business-bay-urban-oasis-14984313.html",
                "listedDate": "2025-08-18T13:44:25Z",
                "isVerified": true,
                "isAvailable": true
            },
            {
                "listingType": "property",
                "propertyId": "14984311",
                "reference": "DPF-S-40377",
                "title": "High Floor | Vacant Apt with Payment Plan",
                "description": "\nBrought to you by Driven Properties, this 2 Bedroom Apartment is located in Urban Oasis, Business Bay.\n\nUnit Details:\n\n\n  * Vacant\n  * High floor \n  * View: Canal and Burj Khalifa View\n  * Kitchen: Open and Fully Fitted\n  * Bathrooms: 3\n  * Built up Area: 1359 sqft\n  * No. of Parking: 1\n  * Furnished\n\nFeatures:\n\n\n  * 2 Balcony\n  * Built in wardrobes\n  * Kitchen Appliances\n  * Lobby in Building\n  * Sea/Water view\n  * Security\n  * Shared Gym\n  * Shared swimming pool\n  * Pets Allowed\n  * Restaurants\n  * Shops\n  * Metro station\n\nBusiness Bay is a contemporary financial district packed with corporate high-rises, stylish apartment buildings, and swanky hotels.\n\nAsk us about:\n\n\n  * Mortgage Advisory\n  * Property Management\n  * Holiday Homes\n  * Interior Design\n\nVisit our offices across Dubai&#39;s most popular communities including:\n\n\n  * Downtown Dubai\n  * Business Bay\n  * Dubai Creek Harbour\n  * Jumeirah Village Circle\n  * Dubai Hills Estate\n",
                "price": {
                    "value": 2960000,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "11418",
                    "name": "Urban Oasis",
                    "fullName": "Urban Oasis, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay",
                    "coordinates": {
                        "lat": 25.18434715270996,
                        "lon": 55.259220123291016
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/44c797e78c0e7349316adddeae8f8b21/416/272/MODE/3ec9c8/14984311-0c242o.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/44c797e78c0e7349316adddeae8f8b21/668/452/MODE/4f3634/14984311-0c242o.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "244273",
                    "name": "Maheer Silk",
                    "email": "maher@drivenproperties.com",
                    "phone": "+971562191226",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+DPF-S-40377%0AType%3A+Apartment%0APrice%3A+2%2C960%2C000+AED+%0ALocation%3A+Urban+Oasis+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F14984311%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English",
                        "Arabic"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/b6c1610752d527852cc0cda3ae75757dc79a2d3b/desktop",
                    "social": "https://www.linkedin.com/in/maher-al-selk-706980a"
                },
                "broker": {
                    "id": "948",
                    "name": "Driven Properties",
                    "logo": "https://www.propertyfinder.ae/broker/7/178/98/MODE/6b7674/948-logo.jpg?ctr=ae",
                    "address": "Office 101, Building Emaar Square - Building 3, Downtown Dubai, Sheikh Mohammed bin Rashid Blvd, Dubai, ",
                    "email": "abdullah@driven-properties.com",
                    "phone": "+97144297040"
                },
                "details": {
                    "bedrooms": "2",
                    "bathrooms": "3",
                    "size": {
                        "value": 1359,
                        "unit": "sqft"
                    },
                    "furnished": "YES",
                    "completionStatus": "completed",
                    "rera": "71151340201",
                    "offeringType": "Residential for Sale",
                    "amenities": []
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/apartment-for-sale-dubai-business-bay-urban-oasis-14984311.html",
                "listedDate": "2025-08-18T13:44:22Z",
                "isVerified": true,
                "isAvailable": true
            },
            {
                "listingType": "project",
                "price": {},
                "location": {},
                "agent": {
                    "phone": null,
                    "whatsapp": null
                },
                "broker": {},
                "details": {}
            },
            {
                "listingType": "property",
                "propertyId": "14862541",
                "reference": "H4L-3614574",
                "title": "HIGH FLOOR | BEAUTIFUL VIEW | READY SOON",
                "description": "Modern Comfort | High ROI | Smart Investment Opportunity Studio Apartment for Sale in Peninsula Two, Business Bay | Presented by Homes4Life Real Estate\n\nHomes4Life Real Estate is delighted to present this exceptional studio apartment located in Peninsula Two, a premium waterfront community developed by Select Group. Offering stunning community and canal views, this modern studio combines luxury, location, and lifestyle — making it an ideal choice for both end-users and investors.\n\nProperty Details:\nStudio Apartment\nSize: 408.17 sq. ft\nBest View\nEstimated Completion: Q2 2025\nDeveloper: Select Group\n\nKey Features:\nPremium quality finishes and efficient layout\nState-of-the-art fitness facilities\nLuxurious lifestyle amenities\nUnique waterfront living along the Dubai Canal\nLocated in the heart of Business Bay\nExcellent connectivity to Sheikh Zayed Road, First Al Khail Street &amp; Marasi Drive\nWalking distance to Business Bay Metro Station\nMinutes from Dubai Mall, Burj Khalifa, and Dubai Opera\nHigh rental demand and strong ROI potential\n\nWhether you&#39;re looking for a stylish home in a central location or a high-yield investment, this studio in Peninsula Two offers unmatched value in one of Dubai’s most dynamic districts.\n\nFor more details or to book a viewing, contact Homes4Life Real Estate today.",
                "price": {
                    "value": 1250000,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "11626",
                    "name": "Peninsula Two",
                    "fullName": "Peninsula Two, Peninsula, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay, Peninsula",
                    "coordinates": {
                        "lat": 25.185815811157227,
                        "lon": 55.26625061035156
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/f13a6f700a5a141bc6e4b87269cf1a0d/416/272/MODE/ca1a7e/14862541-b17d3o.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/f13a6f700a5a141bc6e4b87269cf1a0d/668/452/MODE/757630/14862541-b17d3o.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "250210",
                    "name": "Himanshu Deepak Daswani",
                    "email": "himanshu@h4l.ae",
                    "phone": "+971565097427",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+H4L-3614574%0AType%3A+Apartment%0APrice%3A+1%2C250%2C000+AED+%0ALocation%3A+Peninsula+Two+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F14862541%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English",
                        "Hindi"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/d06df666fc4b6a8048c6227d9600bd8de8c000b3/desktop"
                },
                "broker": {
                    "id": "568",
                    "name": "Homes 4 Life Real Estate LLC",
                    "logo": "https://www.propertyfinder.ae/broker/7/178/98/MODE/3fdcc0/568-logo.jpg?ctr=ae",
                    "address": "Office 25-26, Building Oasis Centre Mall, Al Quoz, Oasis mall offices, Dubai, ",
                    "email": "mohsin@homes4life.ae",
                    "phone": "+97143387300"
                },
                "details": {
                    "bedrooms": "studio",
                    "bathrooms": "1",
                    "size": {
                        "value": 408,
                        "unit": "sqft"
                    },
                    "furnished": "NO",
                    "completionStatus": "off_plan",
                    "rera": "71384205894",
                    "offeringType": "Residential for Sale",
                    "amenities": [
                        "Central A/C",
                        "Balcony",
                        "Private Garden",
                        "Shared Pool",
                        "Security",
                        "Covered Parking",
                        "Built in Wardrobes",
                        "Walk-in Closet",
                        "Kitchen Appliances",
                        "View of Landmark",
                        "Pets Allowed",
                        "Shared Gym",
                        "Barbecue Area"
                    ]
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/apartment-for-sale-dubai-business-bay-peninsula-peninsula-two-14862541.html",
                "listedDate": "2025-07-31T13:02:40Z",
                "isVerified": true,
                "isAvailable": true
            },
            {
                "listingType": "property",
                "propertyId": "14918961",
                "reference": "01K2552HEK02W9AKTB3YXGH3PS",
                "title": "Furnished  | Bright studio | vacant multiple",
                "description": "URBAN LUXE REAL ESTATE LLC presents DAMAC Majestine offers a grand experience combining the fine comforts of home with the convenience of serviced living. Located in the ‘platinum square kilometer’ of the Burj area in Dubai, just a short distance away, there are personal shoppers ready to help at the finest designer stores and high-end fashion boutiques, where you can shop to your heart’s desire. The world’s largest mall, its tallest tower &amp; the highest dancing fountain – you couldn’t wish for a more iconic neighborhood.\n\nDETAILS:\n\n* Modern kitchen\n* Modern washroom\n* Gym\n* Swimming pool\n* Barbecue area\n* SPA\n* Jacuzzi\n* Sauna room\n* Lockers\n* Shower rooms\n* Kids play area\n\nUrban Luxe Real Estate LLC supports you in accomplishing your estate needs. We have the industry&#39;s best realtors who empower their Landlords and Tenants. From end-users to investors, we take care of every detail with unparalleled transparency and real-time market insights. Let Urban Luxe Real Estate LLC guide you on your real estate journey!",
                "price": {
                    "value": 800000,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "539",
                    "name": "DAMAC Majestine",
                    "fullName": "DAMAC Majestine, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay",
                    "coordinates": {
                        "lat": 25.186573028564453,
                        "lon": 55.28207015991211
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/0292b47acae3aea2f96e3ad0df1b1080/416/272/MODE/77abd6/14918961-e02e6o.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/0292b47acae3aea2f96e3ad0df1b1080/668/452/MODE/a50f06/14918961-e02e6o.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "204541",
                    "name": "Muhammad Nawaz",
                    "email": "nawaz@urbanluxe.ae",
                    "phone": "+971565050736",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+01K2552HEK02W9AKTB3YXGH3PS%0AType%3A+Apartment%0APrice%3A+800%2C000+AED+%0ALocation%3A+DAMAC+Majestine+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F14918961%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English",
                        "Urdu"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/5f53b36523c139e46c33f28587fda9c209ea6364/desktop",
                    "social": "https://www.linkedin.com/in/muhammad-nawaz-a281a488"
                },
                "broker": {
                    "id": "5239",
                    "name": "Urban Luxe Real Estate L.L.C",
                    "logo": "https://www.propertyfinder.ae/broker/4/178/98/MODE/89ca8b/5239-logo.jpg?ctr=ae",
                    "address": "Office 202, Building Al Zaroni Business Center, Al Barsha, Street 1, Dubai, ",
                    "email": "nawaz@urbanluxe.ae",
                    "phone": "+971509420061"
                },
                "details": {
                    "bedrooms": "studio",
                    "bathrooms": "1",
                    "size": {
                        "value": 457,
                        "unit": "sqft"
                    },
                    "furnished": "YES",
                    "completionStatus": "completed",
                    "rera": "7116789032",
                    "offeringType": "Residential for Sale",
                    "amenities": [
                        "Central A/C",
                        "Balcony",
                        "Shared Pool",
                        "Security",
                        "Covered Parking",
                        "Built in Wardrobes",
                        "Walk-in Closet",
                        "Pets Allowed",
                        "Shared Gym"
                    ]
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/apartment-for-sale-dubai-business-bay-damac-majestine-14918961.html",
                "listedDate": "2025-08-08T16:24:02Z",
                "isVerified": true,
                "isAvailable": true
            },
            {
                "listingType": "property",
                "propertyId": "14865434",
                "reference": "1754031331901",
                "title": "Below OP | Exclusive Deal | High ROI",
                "description": "Property Legacy LLC is pleased to present this elegant studio apartment for sale in Bayz 101 by Danube, Business Bay, Dubai. With a smart layout spanning 373 sq. ft., this stylish residence offers modern living in one of Dubai’s most dynamic and sought-after locations.\n\nAbout the Apartment:\n\nSpacious Studio with a well-designed layout for maximum comfort\n1 Modern Bathroom with high-end fittings\nFully Fitted Kitchen with sleek cabinetry and premium appliances\nFloor-to-Ceiling Windows allowing natural light and stunning city views\nPrivate Balcony offering breathtaking skyline views\nBuilt-in Wardrobes for ample storage\nDesignated Parking Space\n\nSituated in the heart of Business Bay, this brand-new development offers world-class amenities, including a rooftop swimming pool, state-of-the-art gym, spa, kids’ play area, and 24/7 security. Residents enjoy seamless access to Downtown Dubai, Burj Khalifa, Dubai Mall, and top dining and entertainment venues.\n\n A perfect investment opportunity or ideal home for urban living in Dubai! \n\n Contact Property Legacy LLC today for more details or to schedule a private viewing!",
                "price": {
                    "value": 1100000,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "13423",
                    "name": "Bayz101 by Danube",
                    "fullName": "Bayz101 by Danube, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay",
                    "coordinates": {
                        "lat": 25.19183349609375,
                        "lon": 55.260765075683594
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/19606a407ffe4bc716fb1c4fce410e1f/416/272/MODE/633514/14865434-38117o.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/19606a407ffe4bc716fb1c4fce410e1f/668/452/MODE/80ce6c/14865434-38117o.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "267986",
                    "name": "Ahmad Khalifa",
                    "email": "ahmad.khalifa@propertylegacy.com",
                    "phone": "+971506268902",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+1754031331901%0AType%3A+Apartment%0APrice%3A+1%2C100%2C000+AED+%0ALocation%3A+Bayz101+by+Danube+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F14865434%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/db387ca6d7943bda436d07b5fa3fbb63164df38d/desktop"
                },
                "broker": {
                    "id": "5664",
                    "name": "PROPERTY LEGACY PREMIER REAL ESTATE",
                    "logo": "https://www.propertyfinder.ae/broker/1/178/98/MODE/8e0283/5664-logo.jpg?ctr=ae",
                    "address": "Office 107, Building Tower AA1, Jumeirah Lake Towers, Mazaya Business Avenue, Dubai, ",
                    "email": "info@propertylegacy.com",
                    "phone": "+971561382474"
                },
                "details": {
                    "bedrooms": "studio",
                    "bathrooms": "1",
                    "size": {
                        "value": 373,
                        "unit": "sqft"
                    },
                    "furnished": "YES",
                    "completionStatus": "off_plan",
                    "rera": "71592149370",
                    "offeringType": "Residential for Sale",
                    "amenities": [
                        "Central A/C",
                        "Balcony",
                        "Shared Pool",
                        "Security",
                        "Concierge",
                        "Maid Service",
                        "Covered Parking",
                        "Built in Wardrobes",
                        "Walk-in Closet",
                        "Kitchen Appliances",
                        "View of Water",
                        "View of Landmark",
                        "Shared Gym",
                        "Barbecue Area"
                    ]
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/apartment-for-sale-dubai-business-bay-bayz101-by-danube-14865434.html",
                "listedDate": "2025-08-01T06:53:24Z",
                "isVerified": true,
                "isAvailable": true
            },
            {
                "listingType": "property",
                "propertyId": "14964481",
                "reference": "RAAS-NS-CB2BR505",
                "title": "3 Years Payment Plan | 0% Commission and DLD Fee",
                "description": "Raas Real Estate proudly brings you Canal Bay Tower by NED Al Ghurair - a newly launched building in Business Bay that offers serene and luxurious waterfront living. \n \nThis stunning two-bedroom apartment offers a breathtaking view of the Canal and Burj Khalifa and is an ideal choice for your sanctuary within the city.\n\nApartment Features:\n\n- 2 Bedrooms\n- 2 Bathrooms\n- 1 Powder room\n- 1 Big Balcony\n- Built-in wardrobes in all the rooms.\n- Floor to ceiling windows\n- Semi-open Kitchen\n- High Floor\n\n\nProperty Amenities:\n\n- Shared Pool\n- Shared Fitness Gym\n- Lobby in the building\n- 24/7 CCTV security\n- Indoor play area\n- Outdoor play area\n- Near the Dubai Mall\n- Cycling Track\n- 1 Parking\n\nRAAS Real Estate strives to simplify real estate investing by minimizing its complexity. Our extensive industry knowledge and experience in leasing and sales have led us to develop a principle of customizing properties to meet our client’s specific needs while offering expert advice and insights on how to expand and optimize their investments.\n",
                "price": {
                    "value": 2300000,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "13775",
                    "name": "Canal Bay",
                    "fullName": "Canal Bay, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay",
                    "coordinates": {
                        "lat": 25.181777954101562,
                        "lon": 55.276710510253906
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/bf20d1c8a84d729c89485c3ec348b496/416/272/MODE/03a69c/14964481-e2790o.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/bf20d1c8a84d729c89485c3ec348b496/668/452/MODE/3a2134/14964481-e2790o.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "291998",
                    "name": "Mohamed Mahmoud Elataby",
                    "email": "elzakir@raas.ae",
                    "phone": "+971501273963",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+RAAS-NS-CB2BR505%0AType%3A+Apartment%0APrice%3A+2%2C300%2C000+AED+%0ALocation%3A+Canal+Bay+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F14964481%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English",
                        "Arabic"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/c9c3c924ca5aeb238afdc3afdfdf7a9e97d07edc/desktop",
                    "social": "https://www.linkedin.com/in/mohamed-zakeer-4762a3198?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=ios_app"
                },
                "broker": {
                    "id": "5688",
                    "name": "RAAS REAL ESTATE",
                    "logo": "https://www.propertyfinder.ae/broker/2/178/98/MODE/fe53f9/5688-logo.jpg?ctr=ae",
                    "address": "Office GF, Building Canal Bay by Ned, Business Bay, ,, Dubai, ",
                    "email": "info@raas.ae",
                    "phone": "+971501024668"
                },
                "details": {
                    "bedrooms": "2",
                    "bathrooms": "3",
                    "size": {
                        "value": 1328,
                        "unit": "sqft"
                    },
                    "furnished": "NO",
                    "completionStatus": "completed",
                    "rera": "71577382979",
                    "offeringType": "Residential for Sale",
                    "amenities": [
                        "Central A/C",
                        "Balcony",
                        "Shared Pool",
                        "Security",
                        "Covered Parking",
                        "Built in Wardrobes",
                        "Pets Allowed",
                        "Shared Gym",
                        "Lobby in Building",
                        "Children's Pool",
                        "Children's Play Area"
                    ]
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/apartment-for-sale-dubai-business-bay-canal-bay-14964481.html",
                "listedDate": "2025-08-15T08:21:02Z",
                "isVerified": true,
                "isAvailable": true
            },
            {
                "listingType": "property",
                "propertyId": "14995853",
                "reference": "MPSP-12172",
                "title": "Resale | Community View | Handover Q4 2028",
                "description": "\nMetropolitan Premium Properties is proud to present this stylish 2-bedroom apartment in One. B Tower, Business Bay.\nProperty Details and Features:\n2 Bedrooms\nSpacious layout\nHigh Floor\nPremium finishes and modern interiors\nBalcony with stunning views\nInfinity pool overlooking the canal\nDedicated co-working spaces\nHigh-speed elevators with private access\n24/7 concierge and security\nRetail and dining options within the tower\nOne. B Tower is a prestigious residential development in Business Bay, offering a luxurious lifestyle with seamless access to Downtown Dubai. The area is known for its vibrant atmosphere, world-class dining, and proximity to major business hubs.\nThe Metropolitan Group is the leading real estate agency in the UAE. We speak 44+ languages and offer our local and international clients exceptional service, expert advice, and comprehensive property sales, purchases, and rental support.\n",
                "price": {
                    "value": 4176432,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "13890",
                    "name": "One B Tower",
                    "fullName": "One B Tower, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay",
                    "coordinates": {
                        "lat": 25.180381774902344,
                        "lon": 55.25185012817383
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/770ecee8a280264e519dbe51cc77625f/416/272/MODE/99964f/14995853-a645do.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/770ecee8a280264e519dbe51cc77625f/668/452/MODE/cd4ec3/14995853-a645do.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "314474",
                    "name": "Jitu Punjabi",
                    "email": "jeetu.punjabi@mpd.ae",
                    "phone": "+971504854037",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+MPSP-12172%0AType%3A+Apartment%0APrice%3A+4%2C176%2C432+AED+%0ALocation%3A+One+B+Tower+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F14995853%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English",
                        "Hindi",
                        "Gujarati",
                        "Punjabi"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/9bab8215fe19f43d940f54b4241c00296340e13e/desktop",
                    "social": ""
                },
                "broker": {
                    "id": "918",
                    "name": "Metropolitan Premium Properties",
                    "logo": "https://www.propertyfinder.ae/broker/11/178/98/MODE/aab3fc/918-logo.jpg?ctr=ae",
                    "address": "Office Office 1806, Building Business Bay, Business Bay, AL MANARA TOWER, Dubai, PO Box 0",
                    "email": "gm@mpdubai.com",
                    "phone": "+971586488888"
                },
                "details": {
                    "bedrooms": "2",
                    "bathrooms": "2",
                    "size": {
                        "value": 1692,
                        "unit": "sqft"
                    },
                    "furnished": "NO",
                    "completionStatus": "off_plan",
                    "rera": "71652959808",
                    "offeringType": "Residential for Sale",
                    "amenities": [
                        "Study",
                        "Balcony",
                        "Shared Pool",
                        "Security",
                        "Concierge",
                        "Built in Wardrobes",
                        "Pets Allowed",
                        "Shared Gym",
                        "Children's Play Area",
                        "Barbecue Area"
                    ]
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/apartment-for-sale-dubai-business-bay-one-b-tower-14995853.html",
                "listedDate": "2025-08-20T07:36:13Z",
                "isVerified": true,
                "isAvailable": true
            },
            {
                "listingType": "project",
                "price": {},
                "location": {},
                "agent": {
                    "phone": null,
                    "whatsapp": null
                },
                "broker": {},
                "details": {}
            },
            {
                "listingType": "property",
                "propertyId": "14892088",
                "reference": "SOHAD-PBDBS-ST",
                "title": "luxuries Studio | Separate Kitchen  | Vacant  ",
                "description": "EMI Worldwide Real Estate is thrilled to offer this spacious studio apartment available for Sale in Damac Maison Prive, Located in Business Bay, Downtown side.\n\nProperty Details:\n- Studio Apartment.\n- Fully Furnished.\n- Waterfront Building.\n- Mid Floor.\n- Panoramic glass.\n-  Canal View.\n\nAmenities:\n\n- Infiniti Pool.\n- GYM\n- SPA\n- Meeting Areas\n- Restaurants &amp; Cafe.\n- Super Market.\n- Free Valley.\n\nLocation Access:\n\n- Dubai Mall Walking Distance.\n- Burj Khalifa &amp; Fountain Walking Distance.\n- Downton Boulevard Walking Distance.\n- Business Bay Metro Station 5 minutes by car\n- Dubai Airport 20 minutes by car.\n\nDamac Prive is one of the hight demanded buildings in Business Bay in term of long- or short-term rentals even for those who are seeking a calm lifestyle because of the location, in the centre of Business Bay, waterfront building with a direct access to Business Bay Canal.\nA nice entrance with a luxuries loppy that takes you to two Towers A &amp; B, Waiting Areas, Concierge service, valley parking.",
                "price": {
                    "value": 990000,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "12279",
                    "name": "PRIVE BY DAMAC (B)",
                    "fullName": "PRIVE BY DAMAC (B), DAMAC Maison Privé, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay, DAMAC Maison Privé",
                    "coordinates": {
                        "lat": 25.184221267700195,
                        "lon": 55.27580261230469
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/95e664d4b971a2905c8ec78e76ff1db6/416/272/MODE/5d4f55/14892088-05b04o.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/95e664d4b971a2905c8ec78e76ff1db6/668/452/MODE/a197a9/14892088-05b04o.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "268495",
                    "name": "Sohad Sallam",
                    "email": "sohad@emirates-worldwide.com",
                    "phone": "+971504223520",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+SOHAD-PBDBS-ST%0AType%3A+Apartment%0APrice%3A+990%2C000+AED+%0ALocation%3A+PRIVE+BY+DAMAC+%28B%29+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F14892088%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English",
                        "Arabic"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/706073d7736e03c79970797c50b3efb81e5549c3/desktop"
                },
                "broker": {
                    "id": "7764",
                    "name": "EMI WORLDWIDE REAL ESTATE",
                    "logo": "https://www.propertyfinder.ae/broker/5/178/98/MODE/28157d/7764-logo.jpg?ctr=ae",
                    "address": "Office G15, Building 1, Mohammad Bin Rashid Gardens, 1, Dubai, PO Box 0",
                    "email": "alzaabi@emirates-worldwide.com",
                    "phone": "+971504425665"
                },
                "details": {
                    "bedrooms": "studio",
                    "bathrooms": "1",
                    "size": {
                        "value": 449,
                        "unit": "sqft"
                    },
                    "furnished": "YES",
                    "completionStatus": "completed",
                    "rera": "7117780641",
                    "offeringType": "Residential for Sale",
                    "amenities": [
                        "Central A/C",
                        "Shared Pool",
                        "Shared Spa",
                        "Built in Wardrobes",
                        "Kitchen Appliances",
                        "View of Water",
                        "Shared Gym",
                        "Lobby in Building"
                    ]
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/apartment-for-sale-dubai-business-bay-damac-maison-prive-prive-by-damac-b-14892088.html",
                "listedDate": "2025-08-05T09:39:09Z",
                "isVerified": true,
                "isAvailable": true
            },
            {
                "listingType": "property",
                "propertyId": "15043357",
                "reference": "ACT-C-400702MMD3",
                "title": "Fully Furnished | Vacant | Upgraded",
                "description": "Fully Furnished 2-Bedroom Apartment is Available for sale in Aykon City Tower C.\n\nProperty Details:\n• Location: AYKON CITY (2) - Tower C, Business Bay\n• Size: 812.89 SQFT\n• Bedrooms: 2\n• Bathrooms: 2\n• Parking: 1 allocated space\n• Status: Vacant\n• Furnishing: Fully Furnished\n• Floor: High Floor\n\nFeatures:\n• Modern and stylish furniture included\n• Floor-to-ceiling windows with panoramic city views\n• Open-plan living and dining area\n• Built-in wardrobes and premium finishes\n• Fully equipped kitchen with appliances\n• Elegant lobby with 24/7 security and concierge\n• Access to world-class amenities including pool, gym, and kids’ play area\n• Easy access to Sheikh Zayed Road and Downtown Dubai\n• Close to public transport, cafes, restaurants, and shopping outlets\n\nOverview:\nExperience upscale urban living in this beautifully furnished 2-bedroom apartment located in the prestigious AYKON CITY (2) – Tower C, situated in the heart of Business Bay. Spanning 812.89 SQFT, this high-floor unit offers a bright, open space with stunning cityscape views, ideal for professionals or small families seeking a blend of comfort and convenience.",
                "price": {
                    "value": 1850000,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "11980",
                    "name": "Aykon City Tower C",
                    "fullName": "Aykon City Tower C, Aykon City, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay, Aykon City",
                    "coordinates": {
                        "lat": 25.18020248413086,
                        "lon": 55.25243377685547
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/70418af70b71a260b6d09f5d57eb5c29/416/272/MODE/0d6acd/15043357-8d054o.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/70418af70b71a260b6d09f5d57eb5c29/668/452/MODE/c76800/15043357-8d054o.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "205752",
                    "name": "Rabah Kehail",
                    "email": "rabah.k@keyclue.ae",
                    "phone": "+971565484102",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+ACT-C-400702MMD3%0AType%3A+Apartment%0APrice%3A+1%2C850%2C000+AED+%0ALocation%3A+Aykon+City+Tower+C+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F15043357%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English",
                        "Arabic"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/bdd6564f0e59374ade54ce676f61f41e409fbefd/desktop",
                    "social": ""
                },
                "broker": {
                    "id": "5314",
                    "name": "Key Clue Properties LLC",
                    "logo": "https://www.propertyfinder.ae/broker/4/178/98/MODE/47d315/5314-logo.jpg?ctr=ae",
                    "address": "Office 1902, Building The One Tower, Barsha Heights (Tecom), Sheikh Zayed, Dubai, ",
                    "email": "info@keyclue.ae",
                    "phone": "+971556699818"
                },
                "details": {
                    "bedrooms": "2",
                    "bathrooms": "2",
                    "size": {
                        "value": 812,
                        "unit": "sqft"
                    },
                    "furnished": "YES",
                    "completionStatus": "completed",
                    "rera": "7129364992",
                    "offeringType": "Residential for Sale",
                    "amenities": [
                        "Central A/C",
                        "Balcony",
                        "Private Jacuzzi",
                        "Covered Parking",
                        "Built in Wardrobes"
                    ]
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/apartment-for-sale-dubai-business-bay-aykon-city-aykon-city-tower-c-15043357.html",
                "listedDate": "2025-08-27T07:07:49Z",
                "isVerified": true,
                "isAvailable": true
            },
            {
                "listingType": "property",
                "propertyId": "14582031",
                "reference": "ROC-S-1079",
                "title": "Fully  Furnished  | Full Canal View | Top Location",
                "description": "<p>Roca Real Estate is delighted to present this elegantly furnished  property in Binghatti Canal Business Bay Dubai its one of the main central business districts of Dubai. <br/><br/>The area is truly a city within the city, boasting residential, commercial and leisure spaces where luxury comforts designed to blend contemporary elegance with unparalleled comfort.</p>\n<p><strong>Features &amp; Amenities:</strong><br/>-1 Bedroom<br/>-Vacant<br/>-Elegant Interior Finish<br/>-Fully Furnished<br/>-Children&#39;s play area<br/>-Barbecue Area<br/>-Balcony<br/>-Security<br/>-Fully equipped gym<br/>-Sauna<br/>-Infinity Swimming Pool<br/>-Resort-style facilities<br/>-Retail area<br/>-Covered parking 3 parking levels</p>\n<p><br/><strong>Roca Real Estate</strong> believes that buyer and seller hold equal value in every transaction. Our goal is to deliver thoughtful, data-driven guidance that results in confident decisions and lasting satisfaction by aligning closely with our clients&#39; goals, preferences, and expectations, we organize a highly tailored selection of properties or investment ensuring each opportunity is the right fit.<br/><br/><strong>RERA ORN : 33055</strong><br/><strong>PO BOX : 117052</strong></p>",
                "price": {
                    "value": 1900000,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "11732",
                    "name": "Binghatti Canal",
                    "fullName": "Binghatti Canal, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay",
                    "coordinates": {
                        "lat": 25.186084747314453,
                        "lon": 55.28614044189453
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/17f261aec5565e62454bfcf523b92a29/416/272/MODE/b6675e/14582031-0e92eo.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/17f261aec5565e62454bfcf523b92a29/668/452/MODE/db8407/14582031-0e92eo.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "321096",
                    "name": "Metin Sari",
                    "email": "info@roca.ae",
                    "phone": "+971566824189",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+ROC-S-1079%0AType%3A+Apartment%0APrice%3A+1%2C900%2C000+AED+%0ALocation%3A+Binghatti+Canal+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F14582031%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English",
                        "Turkish"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/5c3743d9ed99babcdf0201034c91d047c84aea41/desktop"
                },
                "broker": {
                    "id": "8674",
                    "name": "ROCA REAL ESTATE L.L.C",
                    "logo": "https://www.propertyfinder.ae/broker/2/178/98/MODE/adc70c/8674-logo.jpg?ctr=ae",
                    "address": "Office 1902, Building Ubora Tower, Business Bay, PO Box 117502, Dubai",
                    "email": "info@metinsari.com",
                    "phone": "+971562109094"
                },
                "details": {
                    "bedrooms": "1",
                    "bathrooms": "2",
                    "size": {
                        "value": 717,
                        "unit": "sqft"
                    },
                    "furnished": "YES",
                    "completionStatus": "completed",
                    "rera": "71404355463",
                    "offeringType": "Residential for Sale",
                    "amenities": [
                        "Central A/C",
                        "Balcony",
                        "Shared Pool",
                        "Covered Parking",
                        "Built in Wardrobes",
                        "View of Water",
                        "Shared Gym",
                        "Children's Play Area",
                        "Barbecue Area"
                    ]
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/apartment-for-sale-dubai-business-bay-binghatti-canal-14582031.html",
                "listedDate": "2025-06-24T13:46:28Z",
                "isVerified": true,
                "isAvailable": true
            },
            {
                "listingType": "property",
                "propertyId": "14932060",
                "reference": "DP-S-53115",
                "title": "Genuine Seller | Canal View | High-end Furnished",
                "description": "\nBrought to you by Driven Properties, this studio Bedroom Apartment is located in Trillionaire Residences, Trillionaire Residences, Business Bay.\n\nUnit Details:\n\n\n  * Vacant\n  * Mid Floor with Full View of the Dubai Canal  \n  * View: Dubai Canal \n  * Kitchen: Open and Fully Fitted\n  * Bathrooms: 1\n  * Built up Area: 547.00 square feet\n  * No. of Parking: 1\n  * Furnished\n\nFeatures:\n\n\n  * Balcony\n  * Built in wardrobes\n  * Covered parking\n  * Kitchen Appliances\n  * Lobby in Building\n  * Sea/Water view\n  * Security\n  * Shared Gym\n  * Shared swimming pool\n  * View of Landmark\n  * Private Jacuzzi\n  * Concierge Service\n\nTrillionaire Residences in Business Bay is a luxury waterfront development by Binghatti, offering studios to 2-bedroom apartments with premium finishes and canal views. Residents enjoy upscale amenities like pools, gym, spa services, concierge, and dining options, all within minutes of Downtown Dubai and major highways.\n\nAsk us about:\n\n\n  * Mortgage Advisory\n  * Property Management\n  * Holiday Homes\n  * Interior Design\n\nVisit our offices across Dubai&#39;s most popular communities including:\n\n\n  * Downtown Dubai\n  * Business Bay\n  * Dubai Creek Harbour\n  * Jumeirah Village Circle\n  * Dubai Hills Estate\n",
                "price": {
                    "value": 1800000,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "13106",
                    "name": "Trillionaire Residences",
                    "fullName": "Trillionaire Residences, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay",
                    "coordinates": {
                        "lat": 25.184173583984375,
                        "lon": 55.28052520751953
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/d30c8e48bc8fca6e76ef1b3ed0f169c2/416/272/MODE/f5acf2/14932060-cfa61o.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/d30c8e48bc8fca6e76ef1b3ed0f169c2/668/452/MODE/e06fdb/14932060-cfa61o.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "280845",
                    "name": "Shimaa Youssef",
                    "email": "shimaa@drivenproperties.com",
                    "phone": "+971502769547",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+DP-S-53115%0AType%3A+Apartment%0APrice%3A+1%2C800%2C000+AED+%0ALocation%3A+Trillionaire+Residences+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F14932060%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English",
                        "Arabic"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/660f923c4ff61e12bc61a01e5777e4c40057b07a/desktop",
                    "social": "https://www.linkedin.com/in/shimaa-youssefal-asklany-426983a5"
                },
                "broker": {
                    "id": "948",
                    "name": "Driven Properties",
                    "logo": "https://www.propertyfinder.ae/broker/7/178/98/MODE/6b7674/948-logo.jpg?ctr=ae",
                    "address": "Office 101, Building Emaar Square - Building 3, Downtown Dubai, Sheikh Mohammed bin Rashid Blvd, Dubai, ",
                    "email": "abdullah@driven-properties.com",
                    "phone": "+97144297040"
                },
                "details": {
                    "bedrooms": "studio",
                    "bathrooms": "1",
                    "size": {
                        "value": 547,
                        "unit": "sqft"
                    },
                    "furnished": "YES",
                    "completionStatus": "completed",
                    "rera": "71508659916",
                    "offeringType": "Residential for Sale",
                    "amenities": []
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/apartment-for-sale-dubai-business-bay-trillionaire-residences-14932060.html",
                "listedDate": "2025-08-11T12:24:28Z",
                "isVerified": true,
                "isAvailable": true
            },
            {
                "listingType": "property",
                "propertyId": "15035073",
                "reference": "TPL-S-4242",
                "title": "Fully Furnished | Canal View | Vacant |Inquire Now",
                "description": "<p>Top Class Real Estate Broker is proud to offer this apartment in Mayfair Residency located in Business Bay. <br/><br/>Property Details:<br/>Fully Furnished <br/>1 Bedroom<br/>Balcony with Canal View<br/>Size: 622.69<br/>Sell Price: AED 970,000/-<br/><br/>For more information or to schedule a viewing, call Gurpreet Kaur</p>\n<p>Mayfair Residency is a 22-storey residential building located in Business Bay, Dubai.</p>\n<p>It offers a range of facilities including swimming pools, separate sauna and steam rooms for men and women, a Jacuzzi, gym, rooftop garden, multi-purpose hall, children&#39;s playroom, plenty of underground and surface parking, and 24-hour security.</p>\n<p>Business Bay is a central and popular area in Dubai, easily reached via Al Khail Road and Sheikh Zayed Road. It offers many nearby services like restaurants, metro stations, hospitals, schools, and supermarkets.</p>\n<p> Top Class Real Estate Broker is a family founded real estate company in Dubai operating a traditional UK estate agency model in the United Arab Emirates (UAE). With our highly experienced agents, Top Class Real estate is committed to delivering superior home buying and selling services to Dubai. </p>",
                "price": {
                    "value": 970000,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "2462",
                    "name": "Mayfair Residency",
                    "fullName": "Mayfair Residency, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay",
                    "coordinates": {
                        "lat": 25.181949615478516,
                        "lon": 55.27723693847656
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/e5e5c95753c092f2cf465ad58b93f477/416/272/MODE/dfb95c/15035073-9b58eo.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/e5e5c95753c092f2cf465ad58b93f477/668/452/MODE/cca452/15035073-9b58eo.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "140042",
                    "name": "Gurpreet Kaur",
                    "email": "gurpreet@tcre.ae",
                    "phone": "+971565114647",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+TPL-S-4242%0AType%3A+Apartment%0APrice%3A+970%2C000+AED+%0ALocation%3A+Mayfair+Residency+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F15035073%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English",
                        "Hindi",
                        "Punjabi"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/12d16da8ad0580d00e1cd66ce6cbcda32f983645/desktop",
                    "social": "https://www.linkedin.com/in/gurpreet-kaur-99041047/"
                },
                "broker": {
                    "id": "346",
                    "name": "Top Class Real Estate Broker L.L.C",
                    "logo": "https://www.propertyfinder.ae/broker/5/178/98/MODE/22a517/346-logo.jpg?ctr=ae",
                    "address": "Office Office 204, Building Cayan Business Center, Barsha Heights (Tecom), ,, Dubai, ",
                    "email": "jay@tcre.ae",
                    "phone": "+97143388745"
                },
                "details": {
                    "bedrooms": "1",
                    "bathrooms": "1",
                    "size": {
                        "value": 622,
                        "unit": "sqft"
                    },
                    "furnished": "YES",
                    "completionStatus": "completed",
                    "rera": "7129260200",
                    "offeringType": "Residential for Sale",
                    "amenities": [
                        "Central A/C",
                        "Balcony",
                        "Shared Pool",
                        "Security",
                        "Concierge",
                        "Covered Parking",
                        "Built in Wardrobes",
                        "Kitchen Appliances",
                        "Shared Gym",
                        "Lobby in Building"
                    ]
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/apartment-for-sale-dubai-business-bay-mayfair-residency-15035073.html",
                "listedDate": "2025-08-26T07:01:33Z",
                "isVerified": true,
                "isAvailable": true
            },
            {
                "listingType": "project",
                "price": {},
                "location": {},
                "agent": {
                    "phone": null,
                    "whatsapp": null
                },
                "broker": {},
                "details": {}
            },
            {
                "listingType": "property",
                "propertyId": "14625900",
                "reference": "RKR-EDGE-1BRD",
                "title": "HIGH FLOOR | CITYSCAPE VIEWS | FLEXIBLE PP",
                "description": "Welcome to The Edge – Tower B, a distinctive residential experience curated by the prestigious Select Group, renowned for shaping iconic developments that blend architectural finesse with modern living. Located in the heart of Business Bay, one of Dubai’s most desirable and fast-evolving urban centers, this luxury 1-bedroom apartment offers not just a place to live, but a lifestyle defined by elegance, comfort, and panoramic city views.\n\n\nKey Property Highlights\n1 Spacious Bedroom\n\nCityscape View – Offering dynamic views of Business Bay’s skyline\n\nHigh Floor – Positioned to capture uninterrupted vistas of the city\n\nLocated in Tower B – One of two architecturally harmonious towers\n\nBalcony – Private outdoor space to enjoy the lights and skyline\n\nFloor-to-Ceiling Panoramic Windows – Maximizing light and views\n\nBuilt-in Wardrobes – Sleek and space-efficient storage\n\nOpen-Plan Kitchen, Living &amp; Dining Area – Modern and airy design\n\nAnticipated Handover in 2026 – Flexible investment timeline\n\nUnparalleled Amenities – Designed for a Balanced Lifestyle\nResidents at The Edge enjoy access to an expansive range of resort-style indoor and outdoor amenities, catering to every aspect of modern urban life:\n\nCommunity Infinity Swimming Pool – Designed for relaxation and leisure\n\nJacuzzi and Wellness Facilities – Perfect for rejuvenation after a busy day\n\nState-of-the-Art Indoor Gym – Fully equipped with modern machines\n\nOutdoor Fitness Area – A scenic and inspiring workout environment\n\nDedicated Yoga &amp; Meditation Zone – Tranquility amidst the urban energy\n",
                "price": {
                    "value": 1600000,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "14066",
                    "name": "The Edge Tower B",
                    "fullName": "The Edge Tower B, The Edge, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay, The Edge",
                    "coordinates": {
                        "lat": 25.188724517822266,
                        "lon": 55.26833724975586
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/cfcf4c3ac32f2df9e000cc4fc704fc10/416/272/MODE/da319c/14625900-ba1e2o.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/cfcf4c3ac32f2df9e000cc4fc704fc10/668/452/MODE/4f4188/14625900-ba1e2o.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "264035",
                    "name": "Rohan",
                    "email": "rohan@primedale.ae",
                    "phone": "+971501371672",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+RKR-EDGE-1BRD%0AType%3A+Apartment%0APrice%3A+1%2C600%2C000+AED+%0ALocation%3A+The+Edge+Tower+B+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F14625900%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English",
                        "Hindi",
                        "Urdu"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/e1fad04f229984aaf4d66ec15dd59fb98a88ba49/desktop",
                    "social": "https://www.linkedin.com/in/rohanbarnes/"
                },
                "broker": {
                    "id": "5861",
                    "name": "Primedale Real Estate",
                    "logo": "https://www.propertyfinder.ae/broker/1/178/98/MODE/689a79/5861-logo.jpg?ctr=ae",
                    "address": "Office 109, Building Bayswater, Business Bay, BB, Dubai, PO Box 171209",
                    "email": "mahima@primedale.ae",
                    "phone": "+971555143482"
                },
                "details": {
                    "bedrooms": "1",
                    "bathrooms": "1",
                    "size": {
                        "value": 698,
                        "unit": "sqft"
                    },
                    "furnished": "NO",
                    "completionStatus": "off_plan_primary",
                    "rera": "1663280791",
                    "offeringType": "Residential for Sale",
                    "amenities": [
                        "Maids Room",
                        "Central A/C",
                        "Balcony",
                        "Shared Spa",
                        "Security",
                        "Concierge",
                        "Maid Service",
                        "Covered Parking",
                        "Built in Wardrobes",
                        "Walk-in Closet",
                        "Kitchen Appliances",
                        "View of Landmark",
                        "Shared Gym",
                        "Lobby in Building",
                        "Children's Pool",
                        "Children's Play Area",
                        "Barbecue Area",
                        "Vastu-compliant"
                    ]
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/apartment-for-sale-dubai-business-bay-the-edge-the-edge-tower-b-14625900.html",
                "listedDate": "2025-06-30T12:41:13Z",
                "isVerified": false,
                "isAvailable": true
            },
            {
                "listingType": "property",
                "propertyId": "14807371",
                "reference": "DUB012520510",
                "title": "Luxury High Floor Penthouse with Private Pool",
                "description": "Knight Frank is proud to present this spacious and elegantly designed 6-bedroom penthouse in the prestigious Amna Tower offers an exceptional investment opportunity in the heart of Business Bay.\n\nDiscover Amna Tower, one of the prestigious residential towers within Al Habtoor City, nestled along the scenic Dubai Water Canal in Business Bay.\n\nProperty Features:\n- 6 bedrooms\n- 7 bathrooms\n- Maid&#39;s room\n- Size: 10,149 sq ft\n- 3 parking spaces\n- Private pool\n- Dubai skyline and canal views\n- Open-plan kitchen with high-end appliances\n- High-quality finishing throughout\n- Private balcony offering stunning sea and canal views\n- Built-in wardrobes\n- Floor-to-ceiling windows\n\nAmenities:\n- 24/7 security and concierge services\n- State-of-the-art gym and fitness facilities\n- Swimming pool with sun deck\n- Covered parking\n- Easy access to Downtown Dubai, Sheikh Zayed Road &amp; Dubai Mall\n\nAsking price: AED 35,000,000\nAgent: Ralph Kondakji\nTrakheesi: 71361415463\n\nAmna Tower combines sleek architectural design, unrivaled waterfront access, and a rich array of premium facilities—crafted for those seeking an elevated urban lifestyle in the heart of Dubai. \n\nIf you would like more information or to arrange a viewing, please contact our Senior Client Advisor Ralph Kondakji.\n\nFinance is available on this property through Knight Frank Mortgage Services.",
                "price": {
                    "value": 35000000,
                    "currency": "AED",
                    "period": "sell"
                },
                "location": {
                    "id": "8452",
                    "name": "Amna",
                    "fullName": "Amna, Al Habtoor City, Business Bay, Dubai",
                    "pathName": "Dubai, Business Bay, Al Habtoor City",
                    "coordinates": {
                        "lat": 25.183345794677734,
                        "lon": 55.256229400634766
                    }
                },
                "images": [
                    {
                        "small": "https://www.propertyfinder.ae/property/365d401d12411acef6755b19e286c410/416/272/MODE/fa6065/14807371-53a80o.jpg?ctr=ae",
                        "medium": "https://www.propertyfinder.ae/property/365d401d12411acef6755b19e286c410/668/452/MODE/9dfcb1/14807371-53a80o.jpg?ctr=ae"
                    }
                ],
                "agent": {
                    "id": "309173",
                    "name": "Ralph Kondakji",
                    "email": "ralph.kondakji@me.knightfrank.com",
                    "phone": "+971565072696",
                    "whatsapp": "https://api.whatsapp.com/send?phone=+97145560345&text=Hello%2C%0AI+would+like+to+get+more+information+about+this+property%3A+%0A+%0AReference%3A+DUB012520510%0AType%3A+Penthouse%0APrice%3A+35%2C000%2C000+AED+%0ALocation%3A+Amna+%0ALink%3A+https%3A%2F%2Fwww.propertyfinder.ae%2Fto%2F14807371%2Fen+%0A+%0AAny+changes+made+to+this+message+will+result+in+the+enquiry+not+being+sent+to+the+agent.",
                    "languages": [
                        "English",
                        "Arabic",
                        "French"
                    ],
                    "image": "https://www.propertyfinder.ae/images/pf_agent/picture/c27541e05b97f0f1a7f243abdd144b56e4e0c429/desktop",
                    "social": "http://linkedin.com/in/ralphkondakji"
                },
                "broker": {
                    "id": "1084",
                    "name": "Knight Frank",
                    "logo": "https://www.propertyfinder.ae/broker/6/178/98/MODE/5c409e/1084-logo.jpg?ctr=ae",
                    "address": "Office 39th Floor, Building Media One Hotel, Dubai Media City, n/a, Dubai, ",
                    "email": "tonilou.velasquez@me.knightfrank.com",
                    "phone": "+97144512000"
                },
                "details": {
                    "bedrooms": "6",
                    "bathrooms": "7",
                    "size": {
                        "value": 10149,
                        "unit": "sqft"
                    },
                    "furnished": "YES",
                    "completionStatus": "completed",
                    "rera": "71361415463",
                    "offeringType": "Residential for Sale",
                    "amenities": [
                        "Maids Room",
                        "Central A/C",
                        "Balcony",
                        "Shared Pool",
                        "Shared Spa",
                        "Security",
                        "Built in Wardrobes",
                        "Walk-in Closet",
                        "View of Water",
                        "Shared Gym",
                        "Lobby in Building"
                    ]
                },
                "shareUrl": "https://www.propertyfinder.ae/en/plp/buy/penthouse-for-sale-dubai-business-bay-al-habtoor-city-amna-14807371.html",
                "listedDate": "2025-07-23T10:42:55Z",
                "isVerified": true,
                "isAvailable": true
            }
        ]
    },
    "status": "success",
    "timeStamp": "2025-09-02T18:23:58.393Z",
    "statusCode": 200
}
```

</details>

---

If you'd like, I can:


## 3) Municipality lookup 

- Endpoint: `https://api.v2.keypilot.io/v1/property/muncipility`
- Method: POST
- Description: Lookup municipal information using DN number and sub-number.


Request body (JSON):
```json
{
	"dnNumber": "345",
	"dnSubNumber": "749"
}
```

Original curl:
```bash
curl -X POST 'https://api.v2.keypilot.io/v1/property/muncipility' \
	-H "Content-Type: application/json" \
	-d '{"dnNumber":"345","dnSubNumber":"749"}'
```

<details>
<summary>Response (example)</summary>

```json
{
    "data": {
        "status": "success",
        "message": "Property status by title deed fetched successfully",
        "responseStatus": 200,
        "result": {
            "projectDetails": {
                "status": 200,
                "timestamp": "2025-08-31T12:21:55.177Z",
                "responseCode": "Success",
                "result": {
                    "project": {
                        "location": {
                            "coordinates": {
                                "latitude": 25.19739999,
                                "longitude": 55.27899191
                            },
                            "street": "The Dubai Mall, Burj Khalifa",
                            "state": "Dubai",
                            "country": "United Arab Emirates"
                        },
                        "title": {
                            "number": "1461",
                            "name": "The Dubai Mall",
                            "totalArea": 1607909.96,
                            "totalUnits": 2139,
                            "completion": 100,
                            "status": "Finished",
                            "completionDate": "2008-08-01T00:00:00",
                            "startDate": "2004-10-01T00:00:00",
                            "registrationDate": "2014-01-26T13:09:00",
                            "escrow": {
                                "agent": null,
                                "account": "-"
                            },
                            "developer": {
                                "name": "Emaar Properties (P.J.S.C)",
                                "logo": "https://mobile.dubailand.gov.ae/Repository/developers/555.png",
                                "contact": {
                                    "phone": "971-4-3673333",
                                    "email": "matrooshi@emaar.ae",
                                    "website": "https://www.emaar.com/"
                                }
                            },
                            "buildings": [
                                {
                                    "name": "The Dubai Mall",
                                    "floorCount": 11
                                },
                                {
                                    "name": "The Dubai Mall Residences",
                                    "floorCount": 25
                                },
                                {
                                    "name": "The Address Dubai Mall Hotel",
                                    "floorCount": 2
                                }
                            ],
                            "media": {
                                "url": "http://mobile.dubailand.gov.ae/Repository/Projects/Dubai Mall_1625304075.jpg"
                            },
                            "unitTypes": [
                                {
                                    "type": "Commercial",
                                    "rooms": [
                                        {
                                            "type": "PENTHOUSE",
                                            "count": "3"
                                        },
                                        {
                                            "type": "NA",
                                            "count": "3"
                                        },
                                        {
                                            "type": "Shop",
                                            "count": "1683"
                                        },
                                        {
                                            "type": "1 B/R",
                                            "count": "1"
                                        }
                                    ]
                                },
                                {
                                    "type": "Residential",
                                    "rooms": [
                                        {
                                            "type": "Studio",
                                            "count": "220"
                                        },
                                        {
                                            "type": "1 B/R",
                                            "count": "176"
                                        },
                                        {
                                            "type": "2 B/R",
                                            "count": "25"
                                        },
                                        {
                                            "type": "3 B/R",
                                            "count": "28"
                                        }
                                    ]
                                }
                            ],
                            "sizes": [
                                569.31,
                                1100273.36,
                                18112.44,
                                67.71,
                                88.39,
                                568.9,
                                290.2,
                                497.72
                            ],
                            "inspections": []
                        }
                    }
                }
            },
            "bigQueryResult": null,
            "propertyStatus": {
                "status": 200,
                "timestamp": "2025-08-31T12:21:55.177Z",
                "responseCode": "Success",
                "result": {
                    "project": {
                        "location": {
                            "coordinates": {
                                "latitude": 25.19739999,
                                "longitude": 55.27899191
                            },
                            "street": "The Dubai Mall, Burj Khalifa",
                            "state": "Dubai",
                            "country": "United Arab Emirates"
                        },
                        "title": {
                            "number": "1461",
                            "name": "The Dubai Mall",
                            "totalArea": 1607909.96,
                            "totalUnits": 2139,
                            "completion": 100,
                            "status": "Finished",
                            "completionDate": "2008-08-01T00:00:00",
                            "startDate": "2004-10-01T00:00:00",
                            "registrationDate": "2014-01-26T13:09:00",
                            "escrow": {
                                "agent": null,
                                "account": "-"
                            },
                            "developer": {
                                "name": "Emaar Properties (P.J.S.C)",
                                "logo": "https://mobile.dubailand.gov.ae/Repository/developers/555.png",
                                "contact": {
                                    "phone": "971-4-3673333",
                                    "email": "matrooshi@emaar.ae",
                                    "website": "https://www.emaar.com/"
                                }
                            },
                            "buildings": [
                                {
                                    "name": "The Dubai Mall",
                                    "floorCount": 11
                                },
                                {
                                    "name": "The Dubai Mall Residences",
                                    "floorCount": 25
                                },
                                {
                                    "name": "The Address Dubai Mall Hotel",
                                    "floorCount": 2
                                }
                            ],
                            "media": {
                                "url": "http://mobile.dubailand.gov.ae/Repository/Projects/Dubai Mall_1625304075.jpg"
                            },
                            "unitTypes": [
                                {
                                    "type": "Commercial",
                                    "rooms": [
                                        {
                                            "type": "PENTHOUSE",
                                            "count": "3"
                                        },
                                        {
                                            "type": "NA",
                                            "count": "3"
                                        },
                                        {
                                            "type": "Shop",
                                            "count": "1683"
                                        },
                                        {
                                            "type": "1 B/R",
                                            "count": "1"
                                        }
                                    ]
                                },
                                {
                                    "type": "Residential",
                                    "rooms": [
                                        {
                                            "type": "Studio",
                                            "count": "220"
                                        },
                                        {
                                            "type": "1 B/R",
                                            "count": "176"
                                        },
                                        {
                                            "type": "2 B/R",
                                            "count": "25"
                                        },
                                        {
                                            "type": "3 B/R",
                                            "count": "28"
                                        }
                                    ]
                                }
                            ],
                            "sizes": [
                                569.31,
                                1100273.36,
                                18112.44,
                                67.71,
                                88.39,
                                568.9,
                                290.2,
                                497.72
                            ],
                            "inspections": []
                        }
                    }
                }
            },
            "serviceChargeResult": {
                "timeStamp": "2025-08-31T16:21:58.8174594+04:00",
                "responseCode": "Success",
                "validationErrorsList": [],
                "response": {
                    "startDate": "2023-01-01T20:00:00",
                    "endDate": "2023-12-31T20:00:00",
                    "propertyManager": {
                        "identity": 146233,
                        "nameEn": "DEYAAR COMMUNITY MANAGEMENT L.L.C",
                        "nameAr": "ديار لإدارة المجمعات ش.ذ.م.م",
                        "parentId": 0
                    },
                    "accountDetail": {
                        "bank": {
                            "englishName": "Mashreq Bank PSC",
                            "arabicName": "بنك المشرق"
                        },
                        "generalAccountTitle": "DT 1",
                        "generalIBAN": "AE330330000019000063226",
                        "reservedAccountTitle": "DT 1 R",
                        "reservedIBAN": "AE220330000019000063230"
                    },
                    "serviceCharges": [
                        {
                            "categoryId": 1,
                            "categoryName": {
                                "englishName": "Services",
                                "arabicName": "خدمات"
                            },
                            "cost": 0.61,
                            "chargeTypeId": 1,
                            "chargeTypeName": {
                                "englishName": "General Fund",
                                "arabicName": "المبلغ العام"
                            },
                            "isFixedService": false
                        },
                        {
                            "categoryId": 2,
                            "categoryName": {
                                "englishName": "Maintenance",
                                "arabicName": "صيانة"
                            },
                            "cost": 0.22,
                            "chargeTypeId": 1,
                            "chargeTypeName": {
                                "englishName": "General Fund",
                                "arabicName": "المبلغ العام"
                            },
                            "isFixedService": false
                        },
                        {
                            "categoryId": 3,
                            "categoryName": {
                                "englishName": "Improvement",
                                "arabicName": "التطوير والتحسين"
                            },
                            "cost": 0.11,
                            "chargeTypeId": 1,
                            "chargeTypeName": {
                                "englishName": "General Fund",
                                "arabicName": "المبلغ العام"
                            },
                            "isFixedService": false
                        },
                        {
                            "categoryId": 5,
                            "categoryName": {
                                "englishName": "Utilities Services",
                                "arabicName": "المرافق"
                            },
                            "cost": 0.57,
                            "chargeTypeId": 1,
                            "chargeTypeName": {
                                "englishName": "General Fund",
                                "arabicName": "المبلغ العام"
                            },
                            "isFixedService": false
                        },
                        {
                            "categoryId": 6,
                            "categoryName": {
                                "englishName": "Management Services ",
                                "arabicName": "خدمات الإدارة"
                            },
                            "cost": 1.12,
                            "chargeTypeId": 1,
                            "chargeTypeName": {
                                "englishName": "General Fund",
                                "arabicName": "المبلغ العام"
                            },
                            "isFixedService": false
                        },
                        {
                            "categoryId": 7,
                            "categoryName": {
                                "englishName": "Insurance",
                                "arabicName": "تأمين"
                            },
                            "cost": 0.64,
                            "chargeTypeId": 1,
                            "chargeTypeName": {
                                "englishName": "General Fund",
                                "arabicName": "المبلغ العام"
                            },
                            "isFixedService": false
                        },
                        {
                            "categoryId": 8,
                            "categoryName": {
                                "englishName": "Master Community ",
                                "arabicName": "المجمع الرئيس"
                            },
                            "cost": 2.18,
                            "chargeTypeId": 1,
                            "chargeTypeName": {
                                "englishName": "General Fund",
                                "arabicName": "المبلغ العام"
                            },
                            "isFixedService": false
                        },
                        {
                            "categoryId": 12,
                            "categoryName": {
                                "englishName": "Reserved Fund",
                                "arabicName": "الصندوق الاحتياطي"
                            },
                            "cost": 1.45,
                            "chargeTypeId": 2,
                            "chargeTypeName": {
                                "englishName": "Reserved Fund",
                                "arabicName": "مبلغ الإحتياط"
                            },
                            "isFixedService": false
                        },
                        {
                            "categoryId": 9,
                            "categoryName": {
                                "englishName": "Income",
                                "arabicName": "الإيرادات"
                            },
                            "cost": -0.07,
                            "chargeTypeId": 1,
                            "chargeTypeName": {
                                "englishName": "General Fund",
                                "arabicName": "المبلغ العام"
                            },
                            "isFixedService": false
                        }
                    ],
                    "request": {
                        "areaId": 0,
                        "masterCommunityId": 0,
                        "projectId": 0,
                        "usageId": 6,
                        "year": 2023,
                        "propertyGroupId": 192385903,
                        "tabuPropertyId": 0,
                        "masterCommunityName": null,
                        "areaName": null,
                        "projectName": null,
                        "propertyGroupName": null,
                        "managementCompanyId": 0,
                        "managementCompanyName": null
                    },
                    "additionalData": null
                }
            },
            "errorMessage": [
                {}
            ]
        },
        "timestamp": "2025-08-31T12:21:58.766Z"
    },
    "freshness": 685742
}
```

</details>

---

## 4) Makani lookup

- Endpoint: `https://api.v2.keypilot.io/v1/property/makani`
- Method: POST
- Description: Retrieve property info by Makani number.


Request body (JSON):
```json
{
	"makaniNumber": "2928496400"
}
```

Original curl:
```bash
curl -X POST 'https://api.v2.keypilot.io/v1/property/makani' \
	-H "Content-Type: application/json" \
	-d '{"makaniNumber":"2928496400"}'
```

<details>
<summary>Response (example)</summary>

```json
{
    "status": "success",
    "message": "Property status by Makani number fetched successfully",
    "responseStatus": 200,
    "result": {
        "projectDetails": {},
        "bigQueryResult": null,
        "propertyStatus": {
            "propInfo": {
                "Result": {
                    "DeveloperArabic": null,
                    "DeveloperEnglish": null,
                    "LandStatus": "PREMISED",
                    "LandTypeArabic": "تجارى",
                    "LandTypeEnglish": "Commercial",
                    "ProjectArabic": null,
                    "ProjectEnglish": null,
                    "PropertyArabicDescription": "ارض - تجارية - عيال ناصر - 208",
                    "PropertyEnglishDescription": "Land - Commercial - Eyal Nasser - 208",
                    "PropertyID": 52999,
                    "PropertyLocation": null,
                    "PropertySubTypeArabic": "تجارية",
                    "PropertySubTypeEnglish": "Commercial",
                    "RoomsArabic": null,
                    "RoomsEnglish": null,
                    "LandNo": "208",
                    "LandSubNo": "0",
                    "DMNo": "116",
                    "DMSubNo": "502",
                    "CanConvertToFreehold": false,
                    "AdditionalData": null,
                    "IsSuccess": true,
                    "ValidationErrors": []
                },
                "Id": 30536857,
                "Exception": null,
                "Status": 5,
                "IsCanceled": false,
                "IsCompleted": true,
                "IsCompletedSuccessfully": true,
                "CreationOptions": 0,
                "AsyncState": null,
                "IsFaulted": false
            },
            "propStatus": {
                "Result": {
                    "Area": 1332.7,
                    "BlockingHistory": null,
                    "IsFreeHold": false,
                    "IsMortgaged": false,
                    "IsRegistered": true,
                    "IsRestrained": false,
                    "IsRestricted": false,
                    "LastTitleDeed": "69795/2017",
                    "MakaniNumber": "0",
                    "NumberOfOwners": 1,
                    "OwnerTypes": "AUTHORITY",
                    "PreRegistrationNumber": null,
                    "PropertyId": 52999,
                    "PropertyStatuses": [
                        {
                            "ArabicStatus": "ملك حر",
                            "EnglishStatus": "FREE",
                            "MortgageeName": null,
                            "StatusCode": "FREE"
                        }
                    ],
                    "RestrainList": null,
                    "TotalCount": 1,
                    "AdditionalData": null,
                    "IsSuccess": true,
                    "ValidationErrors": []
                },
                "Id": 30537075,
                "Exception": null,
                "Status": 5,
                "IsCanceled": false,
                "IsCompleted": true,
                "IsCompletedSuccessfully": true,
                "CreationOptions": 0,
                "AsyncState": null,
                "IsFaulted": false
            },
            "otherInfo": {
                "timeStamp": "2025-08-31T16:27:03.2906816+04:00",
                "responseCode": "Empty",
                "validationErrorsList": [],
                "response": {
                    "items": null,
                    "additionalData": null
                }
            },
            "extraInfo": {
                "timeStamp": "2025-08-31T16:27:03.264688+04:00",
                "responseCode": 200,
                "validationErrorsList": [],
                "response": {
                    "result": [
                        {
                            "PROPERTY_TYPE_ID": 1,
                            "PROPERTY_SUB_TYPE_ID": 62,
                            "PARCEL_ID": 1160502,
                            "LNG": 55.30455448,
                            "LAT": 25.27446222,
                            "IS_RENTED": 0,
                            "DEWA_PREMISE": null
                        }
                    ],
                    "additionalData": null
                }
            },
            "metadata": {
                "cacheKey": "property_status_{\"makaniNumber\":\"2928496400\",\"serviceType\":\"SearchByMakani\"}_2025-08-31",
                "timestamp": 1756643224778,
                "steps": [
                    "captcha_token",
                    "prop_info",
                    "prop_status",
                    "other_info",
                    "extra_info"
                ]
            }
        },
        "serviceChargeResult": null,
        "errorMessage": [
            {},
            {}
        ]
    },
    "timestamp": "2025-08-31T12:27:10.736Z"
}
```

</details>

---

## 5) ConstList — list units by building name

- Endpoint: `https://api.v2.keypilot.io/v1/constList/list/units/db/AL MANARAH TOWER`
- Method: POST (example sends an empty data payload)
- Description: Returns units for the specified building/project. The example uses the building name as part of the path.


Original curl (empty body):
```bash
curl -X POST 'https://api.v2.keypilot.io/v1/constList/list/units/db/AL%20MANARAH%20TOWER'
```

<details>
<summary>Response (example)</summary>

```json
{
    "status": "success",
    "message": "Data fetched successfully",
    "responseStatus": 200,
    "result": [
        {
            "units": [
                "1001"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1002"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1003"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1004"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1005"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1006"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1007"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1008"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1009"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "101"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1010"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "102"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "103"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "104"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "105"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "106"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "107"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1101"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1102"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1103"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1104"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1105"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1106"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1107"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1108"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1109"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1110"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1201"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1202"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1203"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1204"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1205"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1206"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1207"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1208"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1209"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1210"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1301"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1302"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1303"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1304"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1305"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1306"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1307"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1308"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1309"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1310"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1401"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1402"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1403"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1404"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1405"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1406"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1407"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1408"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1409"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1410"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1501"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1502"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1503"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1504"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1505"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1506"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1507"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1508"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1509"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1510"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1601"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1602"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1603"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1604"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1605"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1606"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1607"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1608"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1609"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1610"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1701"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1702"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1703"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1704"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1705"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1706"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1707"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1708"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1709"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1710"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1801"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1802"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1803"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1804"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1805"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1806"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1807"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1808"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1809"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1810"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1901"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1902"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1903"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1904"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1905"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1906"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1907"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1908"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1909"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "1910"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2001"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2002"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2003"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2004"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2005"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2006"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2007"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2008"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2009"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "201"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2010"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "202"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "203"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "204"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "205"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "206"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "207"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "208"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "209"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "210"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2101"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2102"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2103"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2104"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2105"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2106"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2107"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2108"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2109"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2110"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2201"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2202"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2203"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2204"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2205"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2206"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2207"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2208"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2209"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2210"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2301"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2302"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2303"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2304"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2305"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2306"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2307"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2308"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2309"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2310"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2401"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2402"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2403"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2404"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2405"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2406"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2407"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2408"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2409"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2410"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2501"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2502"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2503"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2504"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2505"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2506"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2507"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2508"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2509"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2510"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2601"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2602"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2603"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2604"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2605"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2606"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2607"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2608"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2609"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "2610"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "301"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "302"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "303"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "304"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "305"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "306"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "307"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "308"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "309"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "310"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "401"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "402"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "403"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "404"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "405"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "406"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "407"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "408"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "409"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "410"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "501"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "502"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "503"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "504"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "505"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "506"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "507"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "508"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "509"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "510"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "601"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "602"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "603"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "604"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "605"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "606"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "607"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "608"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "609"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "610"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "701"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "702"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "703"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "704"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "705"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "706"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "707"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "708"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "709"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "710"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "801"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "802"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "803"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "804"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "805"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "806"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "807"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "808"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "809"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "810"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "901"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "902"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "903"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "904"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "905"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "906"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "907"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "908"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "909"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "910"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "RETAIL 1"
            ],
            "projectName": "AL MANARAH TOWER"
        },
        {
            "units": [
                "RETAIL 2"
            ],
            "projectName": "AL MANARAH TOWER"
        }
    ],
    "timestamp": "2025-08-31T12:32:51.859Z"
}
```

</details>

Note: URL-encode spaces when calling from scripts or programs. If this endpoint is intended to be a GET, try removing `--data` and using GET instead.

---

## 6) ConstList — project list for query

- Endpoint: `https://api.v2.keypilot.io/v1/constList/ProjectList/Elite Business`
- Method: POST (example uses empty data)
- Description: Returns a list of projects matching the path segment.


Original curl:
```bash
curl 'https://api.v2.keypilot.io/v1/constList/ProjectList/Elite%20Business'
```

<details>
<summary>Response (example)</summary>

```json
{
    "status": "success",
    "message": "Data fetched successfully",
    "responseStatus": 200,
    "result": {
        "status": 200,
        "timestamp": "2025-08-31T12:31:14.805Z",
        "responseCode": "Success",
        "result": {
            "project": [
                {
                    "number": "1868",
                    "name": "Elite Business Bay Residence",
                    "status": "Finished",
                    "completion": 100,
                    "developer": {
                        "name": "Range 4 Developments L.L.C",
                        "rating": "5"
                    },
                    "image": "",
                    "location": "Business Bay"
                }
            ]
        }
    },
    "timestamp": "2025-08-31T12:31:14.805Z"
}
```

</details>
