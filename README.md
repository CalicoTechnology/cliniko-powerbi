# Cliniko Reports for Power BI
We're really excited to release our Power BI reporting solution for Cliniko, providing detailed insights into appointments, invoices, practitioners, and business performance.

You can either use these reports 'as is', create your own reports, and even contribute to this project.   We would love to see what reports and enchantments you create.

## 📊 Available Reports

### Core Reports
We have added some base reports for you to use, or you can create your own from the data available. 

- **Appointments Dashboard**: Total appointments, YTD tracking, YoY growth
- **Financial Overview**: Invoice tracking, revenue analysis, product performance
- **Practitioner Performance**: Hours worked, appointment load, availability
- **Business Metrics**: Overall practice performance and KPIs

### Data Sources
The data sources are directly driven from the [Cliniko API](https://docs.api.cliniko.com/), and includes objects such as:

- Business
- Practitioners
- Appointments
- Appointment Types
- Invoice and Invoice Items 
- Products and Services

If your reports don't need these you can remove them to save load time.  You can also add new queries if you want something which we haven't added. 

## 🛠️ Installation

### Prerequisites

- Power BI Desktop (latest version)
- Cliniko account
- An active User with an API key 

### Setup Instructions

1. **Download the Project**

   **Option A: Using Git**
   ```bash
   git clone https://github.com/tunechr/cliniko-reports.git
   cd cliniko-reports
   ```

   **Option B: Download ZIP File**
   - Go to the [GitHub repository](https://github.com/tunechr/cliniko-reports)
   - Click the green "Code" button
   - Select "Download ZIP" from the dropdown menu
   - Extract the ZIP file to your desired location on your computer
   - Open the extracted folder

2. **Open in Power BI Desktop**
   - Open Power BI Desktop
   - File → Open → Navigate to `powerbi-project/calico-cliniko-base-reportpbip.pbip`

3. **Configure Parameters**

  The report uses several parameters that need to be configured:
   - **APIKey**: Your Cliniko API key
   - **API_BASE**: Your Cliniko subdomain (e.g., https://api.{shard}.cliniko.com/v1)
   - **TimezoneParameter**: Your local timezone for date/time calculations

When you open the report for the first time it will prompt you for your `API Key` and `Base Url`, and `Timezone`.

Read how to [Generate an API Key](https://help.cliniko.com/en/articles/1023957-generate-a-cliniko-api-key)

If you do now know your shard, look at the end of the generated API key where you will see a dash and your shard, e.g. `-au4` or `-uk1`

Check the [Cliniko Documentation](https://docs.api.cliniko.com/guides/urls) for more info on Shards and API keys. 

If you need to change these parameters at a later date, you can configure these via the parameters:

1. In Power BI Desktop, click on **Transform data** in the Home ribbon
2. Go to **Transform data > Edit Parameters**
3. Update the parameters as needed
4. Click **OK**
5. **Refresh Data**
   - Click "Refresh" to load your Cliniko data
   - The initial load may take several minutes depending on data volume

## 🔧 Configuration

### Data Refresh

- **Manual Refresh**: Use the "Refresh" button in Power BI Desktop
- **Scheduled Refresh**: Publish to Power BI Service for automatic updates

## 📈 Usage

## 🔐 Security & Privacy

### API Security
The reports use a parameter for the API key, this mean that if you save this report the key will be in clear text in the report file. This may be OK for reports on your desktop, but please be mindful if you want to contribute to this project and remove any keys. 
### Data Privacy
A general word on security, the reports so pull through personal information from your patients/clients, so please be aware of this when using or publishing the reports. 
### Publishing and Access Control
If you are publishing the reports to something like the Power BI Service, please ensure compliance with healthcare data regulations in your jurisdiction.  This includes setting up access to the reports and the data sources. 

## 🤝 Contributing

We would love it if you were to contribute to the project! Please see our [Contributing Guide](CONTRIBUTING.md) for details.

### Development Setup

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Test thoroughly with sample data
5. Commit your changes (`git commit -m 'Add amazing feature'`)
6. Push to the branch (`git push origin feature/amazing-feature`)
7. Open a Pull Request

## 📝 License

This project is licensed under the GNU Affero General Public License v3.0 - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

- **Issues**: Report bugs or request features via [GitHub Issues](https://github.com/tunechr/cliniko-reports/issues)
- **Documentation**: Check the [Wiki](https://github.com/tunechr/cliniko-reports/wiki) for detailed guides
- **Community**: Join discussions in the [Discussions](https://github.com/yourusername/cliniko-reports/discussions) section

## 🙏 Acknowledgments

- [Cliniko](https://www.cliniko.com) for providing the excellent practice management platform
- [Power BI](https://powerbi.microsoft.com) for the powerful reporting capabilities
- Contributors and community members who help improve this project

## 📋 Roadmap

Check out the [roadmap](https://github.com/users/tunechr/projects/2)

---

**Note**: This is an unofficial project and is not affiliated with or endorsed by Cliniko. Use at your own discretion and ensure compliance with your organization's data policies.
