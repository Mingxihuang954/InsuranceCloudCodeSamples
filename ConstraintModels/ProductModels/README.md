<!-- For these hierarchies it would be nice to have a paragraph at the beginning of the README that says how these can be used. I assume it's not possible to cut and paste or import these into an org. Are these provided just to show what they look like? Is the user expected to recreate them manually? Are there JSON versions of these that can be imported somehow? -->

### Auto Silver

The Auto Silver root product includes bundle-level coverages (Bodily Injury & Property Damage and Medical Payments), and child products to define multiple vehicles. Each vehicle can have its own coverages (Collision, Comprehensive, and Uninsured Motorist) and associated drivers.

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

The Family Health Insurance Comprehensive root product includes a Primary Member with health coverages (Out-Patient, Preventive Care & Wellness, Chronic Disease, and Critical Illness & Surgery). The primary member can have multiple dependent members, each with the same set of available coverages.

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

The Commercial Property Insurance root product includes General Liability Coverage at the bundle level, and child products to define multiple commercial locations (domestic and international). Each location contains buildings (Warehouse and Building) with their own coverages (Burglary and Vandalism), and each building can have equipment (Equipment and Electrical Equipment) with Equipment Coverage.

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