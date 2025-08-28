# N8N Notion Workspace Scanner

Automated Notion workspace scanner that discovers all databases and pages, processes them separately, and creates comprehensive index entries in dedicated tracking databases.

## Features

- **Native Notion Nodes**: Direct API integration using `n8n-nodes-base.notion`
- **Separate Processing**: Databases and pages handled independently with different schemas
- **Index Creation**: Automatic creation of entries in Database Index and Pages Index
- **Usage Tracking**: Monitors and increments usage counters for discovered items
- **Metadata Capture**: Properties count, creation dates, modification times
- **Duplicate Prevention**: Intelligent handling of existing entries

## Workflow Structure

### Trigger
**Cron Schedule**: 3x daily (9 AM, 2 PM, 8 PM) using cron expression `0 9,14,20 * * *`

### Node Types Used
- **Native Notion Nodes**: For direct API integration when available
- **HTTP Request Nodes**: For custom API calls and external service integration  
- **Code Nodes**: For data processing and transformation
- **Error Handling**: Continue-on-fail enabled for resilient execution

## Installation & Setup

### Prerequisites
- N8N instance with proper credentials configured
- Notion API integration with write permissions
- Required service access (database, webhooks, etc.)

### Configuration Steps

1. **Import Workflow**:
   ```bash
   # Download the workflow file from this repository
   curl -O https://raw.githubusercontent.com/midnightmoodboard/n8n-notion-workspace-scanner/main/notion-workspace-scanner.json
   
   # Import into your N8N instance via the UI or API
   ```

2. **Configure Credentials**:
   - Update all credential references to match your N8N setup
   - Ensure proper API tokens and database IDs are configured
   - Test all connections before enabling the workflow

3. **Activate Workflow**:
   - Enable the workflow in your N8N instance
   - Monitor initial executions for any configuration issues
   - Verify data appears in target systems as expected

## Usage

This workflow operates automatically based on its configured triggers. Monitor execution through:
- N8N execution history
- Target system data verification  
- Error logs and notifications

## Error Handling

Comprehensive error handling includes:
- Continue-on-fail enabled for all critical nodes
- Detailed error logging to Notion database
- Graceful handling of service timeouts and connection issues

## Contributing

Feel free to submit issues and pull requests to improve this workflow.

## License

Open source - adapt for your infrastructure needs.
