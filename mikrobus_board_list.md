# mikroBUS add-on board list CSV file format

The document is a comma-separated value (CSV) text document where each line, separated by a
newline character, represents a single record. The first record is a header, describing
the fields in the following records. For more information about CSV, see the
[CSV Wikipedia article](https://en.wikipedia.org/wiki/Comma-separated_values).

Most fields are just plain strings, but some may only include specific string values and
others may be [JSON](https://en.wikipedia.org/wiki/JSON)
formatted strings to nest additional values. JSON was not utilized for
the entirty of the document for a couple of reasons. First, by keeping each board in a single
line, the version control history can be kept very simple, with a single entry being a single
line change. Second, it would be incredibly redundant and error-prone to need to name each
field in each record. By using CSV, it should be readily apparent if any given field is provided
and examples should be readily explorable in your favorite spreadsheet application.

The good news is that most add-on board records won't require JSON, but plenty tools make
it easy for those that do.

I need a clean reference to this: https://git.beagleboard.org/beagleboard/linux/-/blob/v5.10.168-ti-arm64-r111/include/linux/mikrobus.h?ref_type=heads

## Fields

* Add-on board name: String description of official board name from the manufacturer
* Manufacturer: String description of manufacturer, approved by manufacturer, if possible
* Manufacturer part number: String of add-on board part number provided by manufacturer
* Copyright holder: Copyright string which may be multiline if properly formatted
* Product URL: Link to manufacturer's product information and purchase page
* Other comments: Additional comment string which may be multiline
* Status: one of:
  * VERIFIED (kernel ID) - Verified on BeaglePlay with kernel ID (`uname -r`) used
  * OKAY (bbb.io-clickid-manifests version) - Manifest was manually loaded and validated
  * WITH-MODIFICATONS (modifications needed) - Some modifications to hardware or software required
  * LIMITED-FEATURES (limitations) - Support has a limited feature set
  * NEEDS-TESTING (comments) - Testing has not been completed
* KCONFIG: Config strings required to be enabled in the kernel build to include the driver, separated
  by a vertical bar (|) if there is more than one
* PWM Pin State: a string to represent the pin mode of the PWM pin, one of:
  * MIKROBUS\_STATE\_INPUT
  * MIKROBUS\_STATE\_OUTPUT\_HIGH
  * MIKROBUS\_STATE\_OUTPUT\_LOW
  * MIKROBUS\_STATE\_PWM
  * MIKROBUS\_STATE\_SPI
  * MIKROBUS\_STATE\_I2C
  * MIKROBUS\_STATE\_UART
* INT Pin State: same as PWM, but for the INT pin
* RX Pin State: same as PWM, but for the RX pin
* TX Pin State: same as PWM, but for the TX pin
* SCL Pin State: same as PWM, but for the SCL pin
* SDA Pin State: same as PWM, but for the SDA pin
* COPI Pin State: same as PWM, but for the COPI pin
* CIPO Pin State: same as PWM, but for the CIPO pin
* SCK Pin State: same as PWM, but for the SCK pin
* CS Pin State: same as PWM, but for the CS pin
* RST Pin State: same as PWM, but for the RST pin
* AN Pin State: same as PWM, but for the AN pin
* Device Driver ID: 
* Protocol: one of:
   * I2C
   * SPI
   * UART
   * PLATFORM
* Reg
* IRQ Pin
* IRQ Type
* SPI Max Speed
* SPI Mode
* Properties: How do we know when they are GPIO?
* More Devices
