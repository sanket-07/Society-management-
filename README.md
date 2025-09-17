# 🏢 Society Management System — Mermaid Diagrams

Is document me Society Management System ke different diagrams Mermaid.js ke through represent kiye gaye hai.  
Aap isse directly GitHub par preview kar sakte ho ya [Mermaid Live Editor](https://mermaid.live/) me paste karke visualize kar sakte ho.  

---

## 🔹 Flowchart
```mermaid
flowchart LR
    A([Start / Login]) --> B[Onboarding & Setup]
    B --> C[Resident Management]
    C --> D[Finance & Billing]
    C --> E[Complaint Handling]
    C --> F[Visitor & Security]
    C --> G[Amenities Booking]
    C --> H[Communication & Notices]
    D --> I[Reporting & Analytics]
    E --> I
    F --> I
    G --> I
    H --> I
    J[Staff & Vendor Management] --> I
    I --> K([End])
```

---

## 🔹 Class Diagram
```mermaid
classDiagram
    class "Admin / Committee"
    class "Resident"
    class "Security / Gatekeeper"
    class "Staff / Vendors"

    class "Society Management System" {
        +Finance & Billing
        +Complaint & Service
        +Visitor Management
        +Amenities Booking
        +Communication & Notices
        +Reports & Analytics
    }

    "Admin / Committee" --> "Society Management System"
    "Resident" --> "Society Management System"
    "Security / Gatekeeper" --> "Society Management System"
    "Staff / Vendors" --> "Society Management System"
```

---

## 🔹 Sequence Diagrams  

### 🛠 1. Complaint Handling Workflow
```mermaid
sequenceDiagram
    participant Resident
    participant System
    participant Admin
    participant Staff

    Resident->>System: Raise complaint (e.g., water leakage)
    System->>Admin: Notify new complaint
    Admin->>Staff: Assign complaint
    Staff->>System: Update status (In Progress)
    System->>Resident: Notify status update
    Staff->>System: Mark as Resolved
    System->>Resident: Notify resolution
    Resident->>System: Give feedback / Close ticket
```

---

### 💰 2. Finance & Billing Workflow
```mermaid
sequenceDiagram
    participant Admin
    participant System
    participant Resident
    participant Bank

    Admin->>System: Generate monthly bills
    System->>Resident: Notify bill generated
    Resident->>System: Initiate payment
    System->>Bank: Process payment request
    Bank-->>System: Confirm transaction
    System->>Resident: Send payment receipt
    System->>Admin: Update ledger & reports
```

---

### 🛡 3. Visitor Management Workflow
```mermaid
sequenceDiagram
    participant Visitor
    participant Security
    participant System
    participant Resident

    Visitor->>Security: Request entry
    Security->>System: Log visitor details
    System->>Resident: Notify for approval
    Resident->>System: Accept / Reject visitor
    System->>Security: Show approval/rejection
    Security->>Visitor: Allow / Deny entry
    Security->>System: Mark exit when visitor leaves
```

---

### 🎟 4. Amenities Booking Workflow
```mermaid
sequenceDiagram
    participant Resident
    participant System
    participant Admin
    participant Bank

    Resident->>System: Request amenity booking
    System->>System: Check availability
    alt Available
        System->>Resident: Show confirmation & fee
        Resident->>System: Confirm & Pay
        System->>Bank: Process payment
        Bank-->>System: Payment successful
        System->>Resident: Confirm booking
        System->>Admin: Notify booking details
    else Not Available
        System->>Resident: Show unavailability
```
