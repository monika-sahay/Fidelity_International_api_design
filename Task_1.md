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
     * Query Parameters:
           - `status`: Filter risks by their status (e.g., open, closed).
           - `sort`: Sort risks by a specific field, such as dateIdentified.
           - `fields`: Limit the fields returned in the response (e.g., title,riskLevel,status).
           - `page`: The page number for pagination.
           - `per_page`: The number of risks to return per page (for pagination).
           - `q`: Search risks based on a keyword found in title or description.
       * Response 
           * 201 ok
       
                    {
                      "page": 1,
                      "per_page": 20,
                      "total": 100,
                      "total_pages": 5,
                      "risks": [
                        {
                          "riskId": "12345",
                          "title": "Risk title",
                          "riskLevel": "High",
                          "status": "Open",
                          "system": "Affected system",
                          "identifiedBy": "John Doe",
                          "dateIdentified": "2023-09-01"
                        },
                        {
                          "riskId": "67890",
                          "title": "Another risk",
                          "riskLevel": "Medium",
                          "status": "Open",
                          "system": "Another system",
                          "identifiedBy": "Jane Smith",
                          "dateIdentified": "2023-08-20"
                        }
                      ]
                    }

                
        * 500 Internal Server Error:
            ```
            {"error": "Unable to fetch security risks. Please try again later."}
            ```


3. Get Specific Security Risk
     * Method: `GET`
     * Endpoint: `/api/v1/risks/{riskId}`
     * Path Parameter:
     *     'riskId': The unique identifier for the security risk.
     * Response:
        * 200 OK
                
                {
                "riskId": "12345",
                "title": "Risk title",
                "description": "Detailed risk description",
                "riskLevel": "High",
                "status": "Open",
                "system": "Affected system",
                "identifiedBy": "John Doe",
                "dateIdentified": "2023-09-01"
                }
               
          
        * 404 Not Found:
      
                {
                "error": "Risk not found with the provided ID."
                }


4. Update a Security Risk
     * Method: `PUT`
     * Endpoint: `/api/v1/risks/{riskId}`
     * Path Parameter:
     *     'riskId': The unique identifier of the security risk to update.

            {
            "title": "Updated risk title",
            "description": "Updated risk description",
            "riskLevel": "High | Medium | Low",
            "status": "Open | Closed | Under Review"
            }

    * Response:
        * 200 OK:

                {
                "message": "Security risk updated successfully.",
                "riskId": "12345"
                }

        * 400 Bad Request: 

                    {
                    "error": "Invalid update data. Please check and try again."
                    }

        * 404 Not Found
                    {
                      "error": "Risk not found with the provided ID."
                    }


5. Remove a Security Risk
     * Method: `DELETE`
     * Endpoint: `/api/v1/risks/{riskId}`
     * Path Parameter:
    * riskId: The unique identifier of the security risk to be deleted.
    * Response: 
        * 200 OK: 

                {
                "message": "Security risk deleted successfully."
                }

        * 404 Not Found: 

                {
                "error": "Risk not found with the provided ID."
                }

        * 500 Internal Server Error:

                {
                "error": "Unable to delete the risk. Please try again later."
                }


