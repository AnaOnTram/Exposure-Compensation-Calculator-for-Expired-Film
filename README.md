# The Forgotten Time: Expired Film Calculator

## Overview

The Expired Film Calculator is a simple web application designed to help film photographers determine the appropriate ISO settings for expired film stocks. As film ages, its sensitivity to light decreases, requiring photographers to adjust their exposure settings to compensate for this degradation. This calculator provides a standardized approach to these adjustments based on film type, original ISO, and expiration date.

## Features

- **Film Type Selection**: Choose between Color Negative (C-41) and Black & White film, which degrade at different rates
- **Original ISO Selection**: Select from standard ISO values ranging from 3 to 3200
- **Expiration Date Input**: Specify the month and year when the film expired
- **Precise Calculation**: Linear compensation model that adds stops based on years expired:
  - C-41 film: 0.1 stop per year of expiry
  - B&W film: 0.05 stop per year of expiry (degrades at half the rate of color film)
- **High ISO Compensation**: Additional adjustment for high sensitivity films (over 400 ISO)
- **Standardized Results**: Recommended ISO settings aligned with standard ISO stops

## How It Works

1. The calculator determines how many years the film has been expired
2. It applies a linear compensation model based on film type:
   - For color negative film: 0.1 stop compensation per year expired
   - For black and white film: 0.05 stop compensation per year expired
3. For high sensitivity films (ISO > 400), it applies additional compensation
4. The calculated ISO is then rounded to the nearest standard ISO value

## Calculation Formula

```
Years Expired = (Current Date - Expiration Date) / 365.25

Base Stops = Years Expired × 0.1 (for C-41) or Years Expired × 0.05 (for B&W)

High ISO Stops = log2(Original ISO / 400) × 0.5 (if Original ISO > 400)

Total Stops = Base Stops + High ISO Stops

Calculated ISO = Original ISO / 2^(Total Stops)

Recommended ISO = Nearest Standard ISO Value
```

## Usage

1. Select your film type (Color Negative or Black & White)
2. Choose the original ISO of your film (as printed on the box)
3. Select the expiration month and year (found on the film box or canister)
4. Click "Calculate"
5. View the results and set your camera to the recommended ISO setting

## Installation

This is a standalone HTML application with no dependencies. To install:

1. Download the complete HTML file
2. Optionally add a background image named "Background.JPG" in the same directory
3. Open the HTML file in any modern web browser

## Browser Compatibility

The Expired Film Calculator is compatible with all modern browsers including:
- Chrome
- Firefox
- Safari
- Edge

## Notes on Film Degradation

- Film degradation can vary significantly based on storage conditions
- Films stored in cooler temperatures (refrigerator/freezer) will degrade more slowly
- Films exposed to heat or humidity will degrade faster
- The calculator provides general guidelines; you may need to adjust based on specific storage history
- Consider bracketing your exposures when working with significantly expired film
