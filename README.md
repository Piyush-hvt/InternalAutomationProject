# Playwright MCP Chatbot

## Overview
This project is a Playwright-based automation and reporting system for the HVT OMS (Order Management System) web application. It includes automated test cases, result logging, and reporting features. The project is structured as a Java Spring Boot application, with Playwright integration for browser automation.

## Project Structure

- `src/main/java/com/example/mcp/playwright/`  
  Contains the main Java source code for the Playwright automation and REST API endpoints.
  - `McpBrowserFunction.java` – Browser utility functions
  - `McpPlaywrightService.java` – Playwright automation logic
  - `PlaywrightChatbotApplication.java` – Spring Boot application entry point
  - `PlaywrightController.java` – REST API controller for Playwright actions
  - `PlaywrightService.java` – Service layer for Playwright operations
  - `ProjectController.java` – Project management endpoints
  - `ResultsWebSocketHandler.java` – WebSocket handler for live results
  - `WebSocketConfig.java` – WebSocket configuration

- `src/main/resources/`
  - `application.yml` – Spring Boot configuration
  - `mcp-servers-config.json` – MCP server configuration
  - `static/` – Static web resources (e.g., `index.html`, `live.html`)

- `data/projects/`  
  Stores project-specific data and reports (e.g., `HVt.json`).

- `pom.xml`  
  Maven build configuration.

- `README.md`  
  Project documentation (this file).

- `screenshot_*.png`  
  Screenshots captured during test execution.

## Test Case Reporting Format

Test case results are stored in JSON files (e.g., `HVt_report.json`). Each file contains:

```
{
  "cases": [
    {
      "log": "...step-by-step log...",
      "name": "Test case name",
      "description": "Test case description",
      "id": "Unique test case ID",
      "screenshot": "Path to screenshot (if any)",
      "status": "SUCCESS" | "FAILURE"
    },
    ...
  ],
  "project": "Project name"
}
```

### Example
```
{
  "cases": [
    {
      "log": "✅ Successfully navigated to: https://oms.hexaview.ai\n...",
      "name": "Too1",
      "description": "1.Navigate to Url ...",
      "id": "case_1751624467719_4645",
      "screenshot": "",
      "status": "SUCCESS"
    }
  ],
  "project": "HVt"
}
```

## How to Run

1. **Build the project:**
   ```
   ./mvnw clean install
   ```
2. **Run the application:**
   ```
   ./mvnw spring-boot:run
   ```
3. **Access the web interface:**
   Open `http://localhost:8080` in your browser.

4. **Trigger test cases:**
   Use the REST API or web interface to trigger Playwright test cases. Results will be saved in the `data/projects/` directory and screenshots in the project root.

## Dependencies
- Java 11 or higher
- Maven
- Playwright (via Java bindings)
- Spring Boot

## Notes
- Test case logs and results are stored in JSON format for easy integration and reporting.
- Screenshots are saved for failed and successful steps as PNG files.
- WebSocket support is available for live result updates.

## Contact
For questions or support, contact the project maintainer.
