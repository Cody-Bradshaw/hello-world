# ***Step One***

PET & OWNER   
(PetName, PetType, PetBreed, PetDOB, OwnerLastName, OwnerFirstName, OwnerPhone, OwnerEmail, Service, Date, Charge)

Functional Dependencies:
 1. **PetName** -->(PetType, PetBreed, PetDOB, OwnerLastName, OwnerFirstName, OwnerPhone, OwnerEmail)
 1. **OwnerEmail** --> (OwnerLastName, OwnerFirstName, OwnerPhone)
 1. **OwnerPhone** --> (OwnerLastName, OwnerFirstName, OwnerEmail)
 
PET & OWNER Candidate Keys: PetName   
**Is every determinant a candidate key?**
NOPE __PetName__, __OwnerEmail__ and __OwnerPhone__ are NOT candidate keys.

## ***Step Two***

Break into two relations: OWNER & PET
 1. **OWNER** (OwnerLastName, OwnerFirstName, OwnerPhone, OwnerEmail)
 1. **PET** (PetName, PetType, PetBreed, PetDOB, Foreign Key, Service, date, charge )

***OWNER:***
 __Functional Dependencies__:
 * **OwnerEmail** --> (OwnerLastName, OwnerFirstName, OwnerPhone)
 * **OwnerPhone** --> (OwnerLastName, OwnerFirstName, OwnerEmail)
 * OWNER Candidate Keys: OwnerPhone, OwnerEmail   
***Is every determinant a candidate key?***
YES OwnerEmail and OwnerPhone are candidate keys!

We can choose pick the primary key from either of the canidates.

We can use __OwnerPhone__ as primary key:

 * **OWNER** (OwnerPhone, OwnerLastName, OwnerFirstName, OwnerEmail)
 * **PET** (PetName, PetType, PetBreed, PetDOB, OwnerPhone,Service, Date, Charge )
Functional Dependencies:
 * **PetName**--> (PetType, PetBreed, PetDOB, OwnerPhone)
  
PET and Service Candidate Keys: PetName   
***Is every determinant a candidate key?***
No PetName is not a candidate key

### ***Step Three***

Break Pet into two relations, PET and SERVICE
 * **OWNER** (OwnerPhone, OwnerLastName, OwnerFirstName, OwnerEmail)
 * **PET** (PetName, PetType, PetBreed, PetDOB, OwnerPhone)
 * **SERVICE** (PetName, Date, Service, Charge)
PET  Functional Dependencies:
 * **PetName** --> (PetType, PetBreed, PetDOB, OwnerPhone)
PET Candidate Keys: PetName   
***Is every determinant a candidate key?***
YES PetName is a candidate key!
#### ***NORMALIZED REALTIONS***

 * **OWNER** (OwnerPhone, OwnerLastName, OwnerFirstName, OwnerEmail)
 * **PET** (PetName, PetType, PetBreed, PetDOB, OwnerPhone)
 * **SERVICE** (PetName, Date, Service, Charge)  
