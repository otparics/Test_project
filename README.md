# Test_project
```mermaid
sequenceDiagram
    participant User
    participant FuelApp
    participant Monday.com
    User->>FuelApp: Use case1- Register with username & Password
    FuelApp->>FuelApp: Add user details to H2 Database
    FuelApp->>User: Registration success ?
    User->>FuelApp: Use case2- Authenticate request: Username & Password
    FuelApp->>FuelApp: Validate user credentail 
    FuelApp->>User: FuelApp_AuthToken
    User->>FuelApp: Use case3- getItems 
    FuelApp->>Monday.com: Query details for given boardID (uses Monday.com_AuthToken)
    Monday.com->>FuelApp: BoardID details
    FuelApp->>User: BoardID details
    FuelApp->>Monday.com: Use case4- Update Workitem for given boardID (uses Monday.com_AuthToken)
    Monday.com->>Monday.com: Update workitem details
    Monday.com->>FuelApp: Update success
    FuelApp->>User: Update success
    Monday.com->>Monday.com: Use case5- Update workitem directly on Monday.com
    User->>FuelApp: getItems 
    FuelApp->>Monday.com: Query details for given boardID (uses Monday.com_AuthToken)
    Monday.com->>FuelApp: Updated workitem details
    FuelApp>>User: Updated workitem details
```
