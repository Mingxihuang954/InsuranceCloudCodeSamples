## Constraints (in English) and Code Samples (in CML)

### AutoSilver

#### Constraint 1
 In the bundle, if the most expensive car over $50,000 and the oldest car is before 2020, the bundle must have a Medical Payment Coverage with $2000 limit


#### Constraint 2
 Car is newer than 2023 must have Collision Coverage with $5000 limit


#### Constraint 3
 Car is older than 2020 and Collision Coverage is selected with $200 deductible must NOT have Uninsured Motorist Coverage


#### Constraint 4
 Driver Age and First Licensed Age must be greater than 16


#### Constraint 5
 If at least one car doesn't have Anti-Theft, at least one driver has accident point greater than 5, and item price for product is over $100:
- Must have BIPD coverage (bodily injury & property damage)
- **Attribute:** Property damage per Accident Limit of BIPD must be hidden
- **Value:** $2000 of Bodily Injury Per Accident Limit of BIPD must be hidden


#### Constraint 6
 Medical Payment covered with limit $1000, standard user
- Must have BIPD with Bodily Injury Per Person Limit $1000


### Family Health Insurance Comprehensive (Medical)

#### Constraint 1
 Primary Member has Outpatient Coverage, and Primary Member is a male over 40 Y/O or is married
- must have PCW (preventive care and wellness) with Dedeuctible Limit = 5000
- must have Chronic Disease Coverage


#### Constraint 2
 Dependent Member is selected and current user is a system admin; Primary member is female, and has at least one single dependent member
- exclude Critical Illness Surgery for Primary Member
- hide attribute Out Network Copay for Primary member's out patient coverage
- hide attribute value Others for Gender for Dependent Member
- add Critical Illness Surgery for Dependent Member


#### Constraint 3
 Dependent Member is younger than 30, primary member's PCW have >= 250 Out_Network_Deductible_Limit
- must have PCW for dependent member with Annual outofpocket limit = 20000


#### Constraint 4
 Primary Member has OutPatient Coverage and is current user profile is a system admin, 
 - Dependent Member must have Chronic Disease Coverage, 
 - Primary Member's Out Patient Coverage must have Doctor visit copay = 10000



#### Constraint 5
 Primarymember.Age > 40 and dependentMember.Age < 30
 - Primary Member MUST have Chronic Disease Coverage
 - Dependent Member MUST have Out Patient Coverage


### Commercial

#### Constraint 1 
IF 
- Commercial General Liability Coverage is selected 
- all Location States are not equal to TX (Texas)
- all Commercial Building Burglary Coverage Limit is less than $50,000
- all Warehouse Building Burglary Coverage is less than $20,000
- sum of Equipment Value of Commercial Building is greater than $100,000

THEN
- set Commercial General Liability Coverage Limit to $50,000


#### Constraint 2
IF
- Commercial General Liability Coverage Limit is less than $2,000,000
- Location State is not equal to NY (New York)
- Building Burglary Coverage Limit is less than $50,000
- General Equipment Value is greater than $100,000 

Then 
- *add* General Equipment Coverage to General Equipment bundle 
- *set* General Equipment coverage Limit to $50,000


#### Constraint 3
IF 
- Equipment is selected and Equipment is in 'Good' Condition
- UserProfile is Admin User
- Building is selected and Building Age is 6
- Location State is NY (added to be mutual exclusive to constraint 2)

THEN
- Exclude EquipmentCoverage; 


#### Constraint 4 
For Location:
- City is Boston -> State needs to be MA
- City is San Francisco -> State needs to be CA


#### Constraint 5
- If Agreed Value of Commercial Property Root > 10000, hide SIC code attribute


#### Constraint 6
IF
- Equipment is selected and at least 1 Equipment.EquipmentCondition = Good
- Building(PC) is selected and BuildingAge = 6

THEN
- Hide CommercialBuilding.Sprinkers Information message : Hide sprinklers
- Hide AttributeValue ‘New’ for Equipment.EquipmentCondition 
- *Add General Liability coverage at root level*  if at least one building age is 6 and at least 1 equipment condition is good