### Auto Silver
```
AUTO SILVER (Root Product)
├── COVERAGES (Product)
│   ├── BODILY INJURY & PROPERTY DAMAGE
│   └── MEDICAL PAYMENTS
│
└── AUTO (Product Classification)
    ├── VEHICLE 1
    │   ├── COLLISION
    │   ├── COMPREHENSIVE
    │   ├── UNINSURED MOTORIST
    │   │
    │   └── DRIVER (Product Classification)
    │       ├── DRIVER 1
    │       ├── DRIVER 2
    │       ├── ...
    │       └── DRIVER N
    │
    ├── VEHICLE 2
    │   ├── COLLISION
    │   ├── COMPREHENSIVE
    │   ├── UNINSURED MOTORIST
    │   │
    │   └── DRIVER (Product Classification)
    │       ├── DRIVER 1
    │       ├── DRIVER 2
    │       ├── ...
    │       └── DRIVER N
    │
    ├── ...
    │
    └── VEHICLE N
        ├── COLLISION
        ├── COMPREHENSIVE
        ├── UNINSURED MOTORIST
        │
        └── DRIVER (Product Classification)
            ├── DRIVER 1
            ├── DRIVER 2
            ├── ...
            └── DRIVER N
```

### Medical (Family Health Insurance Comprehensive)
```
Family Health Insurance Comprehensive (Root Product)
└── PRIMARY MEMBER (Product)
    ├── OUT-PATIENT
    ├── PREVENTIVE CARE & WELLNESS
    ├── CHRONIC DISEASE
    ├── CRITICAL ILLNESS & SURGERY
    │
    └── MEMBER (Product Classification)
        ├── DEPENDENT MEMBER 1
        │   ├── OUT-PATIENT
        │   ├── PREVENTIVE CARE & WELLNESS
        │   ├── CHRONIC DISEASE
        │   └── CRITICAL ILLNESS & SURGERY
        │
        ├── DEPENDENT MEMBER 2
        │   ├── OUT-PATIENT
        │   ├── PREVENTIVE CARE & WELLNESS
        │   ├── CHRONIC DISEASE
        │   └── CRITICAL ILLNESS & SURGERY
        │
        ├── ...
        │
        └── DEPENDENT MEMBER N
            ├── OUT-PATIENT
            ├── PREVENTIVE CARE & WELLNESS
            ├── CHRONIC DISEASE
            └── CRITICAL ILLNESS & SURGERY
```

### Commercial (Commercial Property Insurance)
```
Commercial Property Insurance (Root Product)
├── GENERAL LIABILITY COVERAGE
│
└── COMMERCIAL LOCATION CLASS (Classification)
    ├── LOCATION
    │   └── COMMERCIAL BUILDING CLASS (Classification)
    │       ├── WAREHOUSE
    │       │   ├── BURGLARY COVERAGE
    │       │   ├── VANDALISM COVERAGE
    │       │   │
    │       │   └── COMMERCIAL EQUIPMENT CLASS (Classification)
    │       │       ├── EQUIPMENT
    │       │       │   └── EQUIPMENT COVERAGE
    │       │       │
    │       │       └── ELECTRICAL EQUIPMENT
    │       │           └── EQUIPMENT COVERAGE
    │       │
    │       └── BUILDING
    │           ├── BURGLARY COVERAGE
    │           ├── VANDALISM COVERAGE
    │           │
    │           └── COMMERCIAL EQUIPMENT CLASS (Classification)
    │               ├── EQUIPMENT
    │               │   └── EQUIPMENT COVERAGE
    │               │
    │               └── ELECTRICAL EQUIPMENT
    │                   └── EQUIPMENT COVERAGE
    │
    └── INTERNATIONAL LOCATION
        └── COMMERCIAL BUILDING CLASS (Classification)
            ├── WAREHOUSE
            │   ├── BURGLARY COVERAGE
            │   ├── VANDALISM COVERAGE
            │   │
            │   └── COMMERCIAL EQUIPMENT CLASS (Classification)
            │       ├── EQUIPMENT
            │       │   └── EQUIPMENT COVERAGE
            │       │
            │       └── ELECTRICAL EQUIPMENT
            │           └── EQUIPMENT COVERAGE
            │
            └── BUILDING
                ├── BURGLARY COVERAGE
                ├── VANDALISM COVERAGE
                │
                └── COMMERCIAL EQUIPMENT CLASS (Classification)
                    ├── EQUIPMENT
                    │   └── EQUIPMENT COVERAGE
                    │
                    └── ELECTRICAL EQUIPMENT
                        └── EQUIPMENT COVERAGE
```