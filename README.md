# ServiceNow Hardware Delivery Manifest Generator

A Python tool that automates the creation of delivery manifests for IT hardware inventory movements in ServiceNow.

## The Problem

ServiceNow doesn't natively track inventory movements between stockrooms, which meant manually typing every single barcode into delivery notes - a tedious and error-prone process that could take 15-20 minutes per delivery run.

## The Solution

This script processes ServiceNow CSV exports and automatically generates formatted delivery manifests organized by location and device type. What used to take 15-20 minutes of manual data entry now takes about 2 minutes.

## Features

- **Automatic organization**: Groups items by stockroom location and device model
- **Quantity tracking**: Shows counts for each device type
- **Data validation**: Checks for missing stockroom assignments before processing
- **Copy-paste ready**: Output is formatted to drop directly into ServiceNow work notes
- **User-friendly**: Clear instructions and error messages

## How It Works

1. Export hardware data from ServiceNow as CSV
2. Upload the CSV to the Colab notebook
3. Script processes the data and generates a formatted manifest
4. Copy the output directly into your ServiceNow work notes

## Technologies Used

- Python 3
- pandas (data processing)
- Google Colab (for easy access and file uploads)

## Usage

### One-time Setup
1. Open the notebook in Google Colab
2. Click "Copy to Drive" to create your own copy
3. Bookmark your copy for future use

### Running the Script
1. In ServiceNow, search for all items in your delivery (by barcode/serial number)
2. Select all rows → click the three dots next to any column header → Export → CSV
3. In your Colab copy, click "Run all"
4. Upload your `alm_hardware.csv` file when prompted
5. Copy the generated output and paste into ServiceNow work notes

**Important**: Run this AFTER updating stockrooms in ServiceNow, but BEFORE items are delivered/assigned.

## Sample Output

```
---------- ACC A112 ----------
[(7x) HP 24 LED Monitor 524pf]: 
235261
241410
241420
241421
241422
241423
241451

[(6x) HP EliteBook 8 G1i]: 
241534
241535
241536
241537
241538
241539
```

## Impact

- Eliminated manual barcode entry for delivery documentation
- Reduced documentation time from ~15-20 minutes to ~2 minutes per delivery
- Currently used by our 3-person team to streamline one of the most tedious parts of the job

## Future Improvements

- Direct ServiceNow API integration (eliminate CSV export step)
- Support for additional data fields
- Automated work note posting

## Contributing

This was built to solve a specific workflow problem, but suggestions and improvements are welcome!

## License

MIT License - feel free to adapt for your own inventory tracking needs.
