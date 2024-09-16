#Task 1: Design an API specification

Here's a proposed API specification for the Security Risk Escalation Feature. 
This API handles the creation, adjustment, and removal of security risks, and supports features to streamline risk escalation at Fidelity International.
##API Specification: Security Risk Escalation Feature
Base URL
'''
https://api.fidelity.com/api/v1/security-risk-escalation
'''

# Endpoints
1. Create New Security Risk Assessment
     * Method: `POST`
     * Endpoint: `/api/V1/risks`
     * Request Body: 
     * Description: Specifies the data (usually in JSON format) that needs to be sent to the server in the request. This is used to provide information to the server when creating or updating a resource.
       ```
       {
          "title": "Risk title",
          "description": "Detailed risk description",
          "riskLevel": "High | Medium | Low",
          "identifiedBy": "John Doe",
          "system": "Affected system or component",
          "dateIdentified": "YYYY-MM-DD",
          "status": "Open"
        }
       ```
       * Response:
            - 201 Created:
              ```
              {
                  "message": "Security risk created successfully.",
                  "riskId": "12345"
              }

              ```
            - 400 Bad Request:
              ```
              {
                  "error": "Invalid request data. Please check the fields and try again."
              }
              ```
              
2. Get All Security Risks
     * Method: `GET`
     * Endpoint: `/api/v1/risks`
3. Get Specific Security Risk
     * Method: `GET`
     * Endpoint: `/api/v1/risks/{riskId}`
4. Update a Security Risk
     * Method: `PUT`
     * Endpoint: `/api/v1/risks/{riskId}`
5. Remove a Security Risk
     * Method: `DELETE`
     * Endpoint: `/api/v1/risks/{riskId}`
