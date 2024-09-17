# Fidelity International Technology and Digital Virtual Experience Program - Security Risk Escalation API
Fidelity International virtual job simulations


The following tasks were completed as part of the virtual internship program offered by Fidelity International, focusing on the Technology and Digital team. This repository contains the API specification for the Security Risk Escalation Feature, which handles the creation, adjustment, and removal of security risks. It also supports features to streamline risk escalation at Fidelity International.

For more details and to access the virtual internship program, please visit: Fidelity International Technology and Digital Virtual Experience Program on Forage.

Task 1: Design an API Specification for Security Risk Escalation Feature
This API specification was designed to handle the management of security risks, including creating new risk assessments, retrieving risks, updating, and deleting them.

## Technologies:
    - RESTful API Design
    - JSON
    - HTTP Methods
    - API Endpoints Overview:

## Create New Security Risk Assessment
    - Method: POST
    - Endpoint: /api/v1/risks
    - This endpoint allows users to create a new security risk assessment by providing details like title, description, risk level, system affected, and status.

## Get All Security Risks
    - Method: GET
    - Endpoint: /api/v1/risks
    - Retrieves a paginated list of security risks with query parameters for filtering and sorting.


## Get Specific Security Risk
    - Method: GET
    - Endpoint: /api/v1/risks/{riskId}
    - Fetches detailed information on a specific security risk identified by its unique riskId.

## Update a Security Risk

    - Method: PUT
    - Endpoint: /api/v1/risks/{riskId}
    - Updates the details of an existing security risk with a given riskId.


Remove a Security Risk
    
    - Method: DELETE
    - Endpoint: /api/v1/risks/{riskId}
    - Deletes a security risk based on its riskId.


Technologies and Concepts:
* API Design: This project utilizes standard RESTful API principles for ease of scalability and maintenance.
* Security Considerations: While the primary focus is on risk management, the API can also be extended with further security measures, such as role-based access control.
* Pagination and Filtering: Built-in pagination and filtering for efficient data retrieval.

* (https://forage-uploads-prod.s3.amazonaws.com/completion-certificates/Fidelity%20International/uuNRNEBhDJr2zb94j_Fidelity%20International_SXZnRh9TzXvyq38wA_1726569877107_completion_certificate.pdf)
