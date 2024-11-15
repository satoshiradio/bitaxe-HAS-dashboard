# BitAxe Mining Dashboard for Home Assistant

Welcome to the BitAxe Mining Dashboard project! The BitAxe open-source mining movement has revolutionized small-scale Bitcoin mining, making it accessible and fun. While the BitAxe hardware and firmware are fantastic, monitoring multiple miners can be challenging. This dashboard brings all your BitAxe miners and Satoshi Radio pool stats together in one clean, informative interface.

<img width="2303" alt="image" src="https://github.com/user-attachments/assets/4543b773-ac2b-4f9a-9dc0-836c81ff06b6">

## Features
- Real-time monitoring of multiple BitAxe miners
- Total and per-miner hashrate tracking
- Power consumption and efficiency metrics
- Temperature monitoring with overheat detection
- Integration with Satoshi Radio Mining Pool stats
- Beautiful graphs showing historical performance
- Pool comparison showing your contribution to total pool hashrate

## Prerequisites

### Hardware & Network
- One or more BitAxe miners (Nerdaxe, Supra, Gamma, etc.)
- Home Assistant installation
- BitAxe miners must be on the same network as your Home Assistant server
- Mining on Satoshi Radio Pool (if you want to see pool stats)

### Software
- Home Assistant Core 2023.8.0 or newer
- HACS (Home Assistant Community Store) installed
- Custom Cards Required (install via HACS):
  - mini-graph-card

## ⚠️ Important Notes
- **BACKUP YOUR CONFIG**: Always backup your Home Assistant configuration before making changes
- **NETWORK ACCESS**: Ensure your BitAxe miners have static IP addresses or DHCP reservations
- **POOL SPECIFIC**: This dashboard is designed specifically for the Satoshi Radio Mining Pool

## Installation Steps

### 1. Prepare Your Environment
1. Backup your Home Assistant configuration
2. Install HACS if not already installed
3. Install required custom cards through HACS
4. Note down your BitAxe miners' IP addresses
5. Have your Satoshi Radio Pool user (wallet address) ready

### 2. Add Configuration Files
1. Add to your `secrets.yaml`:
   - Copy content from [secrets.yaml](./secrets.yaml)
   - Replace example values with your actual IPs and wallet address
   
2. Modify your `configuration.yaml`:
   - Copy content from [configuration.yaml](./configuration.yaml)
   - Add to your existing config (don't replace everything!)

3. Create `bitaxe.yaml`:
   - Copy the complete file to your config directory
   - No modifications needed unless adding/removing miners

### 3. Create the Dashboard
1. Navigate to Settings -> Dashboards in Home Assistant
2. Create new dashboard named "BitAxe Mining"
3. Open the Raw Configuration Editor
4. Copy content from [dashboard.yaml](./dashboard.yaml)
5. Save and exit

### 4. Finalize
1. Check your configuration in Home Assistant
2. Restart Home Assistant
3. Access your new dashboard!

## Customization

### Adding More Miners
1. Add new miner IP to `secrets.yaml`
2. Copy a miner section in `bitaxe.yaml`
3. Update template sensors in `configuration.yaml`
4. Add new cards to dashboard if desired

### Removing Miners
1. Remove or comment out relevant sections
2. Update template sensors accordingly

### Modifying Thresholds
- Overheat detection threshold (default 85°C) can be modified in template sensors
- Graph timeframes can be adjusted in dashboard cards

## Troubleshooting

### Common Issues
1. "Sensor Unavailable"
   - Check miner IP address
   - Verify network connectivity
   - Confirm miner is powered on

2. "Pool Stats Missing"
   - Verify wallet address
   - Check pool API status
   - Confirm miners are actually mining

3. "Graphs Not Showing"
   - Verify mini-graph-card is installed
   - Check entity names match your config

## Contributing
Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change.

## Support
- For dashboard issues: Open an issue in this repository
- For pool-related questions: [Satoshi Radio Pool](https://pool.satoshiradio.nl)

## License
[MIT](./LICENSE)

## Acknowledgments
- [BitAxe Community and Project](https://bitaxe.org/) - For creating this amazing open-source miner
- Satoshi Radio Pool Community - For providing an excellent mining pool and the first draft of the dashboard
- Home Assistant Community - For the platform and support
- Bart Mol (https://x.com/Bart_Mol) - For the initial dashboard development

---
Made with ❤️ by the BitAxe Community
