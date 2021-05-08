# ESP32 Wi-Fi CSI Python Parser

This is a Python parser for ESP32 Wi-Fi Channel State Information (CSI). This module allows you to parse and filter CSI data based on the ESP32 CSI specification.

This project uses [ESP CSI Toolkit](https://stevenmhernandez.github.io/ESP32-CSI-Tool/) created by Hernandez and Bulut.

## Installation

Run the following to install:

```python
pip install csiparser
```

## Usage

```python
# Import ESP32 CSI parser
import csiparser

# Parse and filter CSI data
example_csi = (
    csiparser.ESP32("./esp32_dataset/example_csi.csv")
             .filter_by_sig_mode(1)
             .get_csi()
             .remove_null_subcarriers()
             .get_amplitude_from_csi()
             .get_phase_from_csi()
)

# Retrieve example amplitude
example_amplitude = example_csi.amplitude

# Retrieve example phase 
example_phase = example_csi.phase
```
_See [Examples](./examples) directory for more examples._

## License
Distributed under the MIT License. See LICENSE for more information.
