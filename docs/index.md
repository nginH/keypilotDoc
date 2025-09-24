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
{

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

