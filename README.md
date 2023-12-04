# IoT Project with AWS, DynamoDB, Timestream, and Grafana

This project involves setting up an IoT system using an ESP32 with a DHT11 sensor and integrating it with AWS services, specifically AWS IoT Core, DynamoDB, Timestream, and Grafana.

## Project Overview

The goal of this project is to collect sensor data from the ESP32, securely transmit it to AWS IoT Core, store it in both DynamoDB and Timestream, and visualize the data using Grafana.

## Setup Instructions

Follow these steps to set up and run the project:

1. **Create a Thing in AWS IoT Core:**
   - Navigate to the AWS IoT Core console.
   - Create a Thing for your ESP32 and download the security certificates and private keys for secure communication.

2. **Define an IoT Policy:**
   - Create an IAM policy and associate it with your Thing to define the actions your device can perform.
   - Ensure the IAM policy has the necessary permissions for sending and receiving messages.

3. **Configure Wi-Fi Connection on ESP32:**
   - In the ESP32 code, use WiFiClientSecure to establish a secure Wi-Fi connection to your network.

4. **Set Up Connection to AWS IoT Core on ESP32:**
   - Configure the ESP32 with the certificates and keys downloaded earlier to connect to AWS IoT Core.
   - Define topics for publishing and subscribing to messages.

5. **Send Sensor Values to AWS IoT Core:**
   - Implement the ESP32 code to read sensor values from DHT11 and send them as JSON messages to AWS IoT Core.

6. **Store Sensor Values in DynamoDB with Lambda:**
   - Create a DynamoDB table to store sensor values.
   - Use the provided Lambda function to process and store incoming messages in DynamoDB.

    ```python
    [Lambda function code]
    ```

7. **Store Time-Series Data in Timestream:**
   - Set up a Timestream database for storing time-series sensor values.
   - Configure another Lambda function to process and store sensor values in Timestream.

8. **Configure IAM Roles:**
   - Create IAM roles with the necessary permissions for Lambda functions to interact with DynamoDB and Timestream.

9. **Connect to Grafana:**
   - Install and configure Grafana to connect to DynamoDB and Timestream as data sources.
   - Create graphical dashboards to visualize and analyze sensor values over time.

## Project Structure

- `ESP32_Code`: Contains the code to be uploaded to the ESP32 device.
- `Lambda_Functions`: Contains Lambda function code for processing and storing data in DynamoDB and Timestream.

## Dependencies

List any dependencies or prerequisites that users need to install before running the project.




