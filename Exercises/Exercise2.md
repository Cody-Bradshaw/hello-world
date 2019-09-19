# Step One

PET and OWNER (PetName, PetType, PetBreed, PetDOB, OwnerLastName, OwnerFirstName, OwnerPhone, OwnerEmail, Service, Date, Charge)

Functional Dependencies:
 * PetName -->(PetType, PetBreed, PetDOB, OwnerLastName, OwnerFirstName, OwnerPhone, OwnerEmail)
 * OwnerEmail --> (OwnerLastName, OwnerFirstName, OwnerPhone)
 * OwnerPhone --> (OwnerLastName, OwnerFirstName, OwnerEmail)
 
PET and OWNER Candidate Keys: PetName
Is every determinant a candidate key?
NO PetName, OwnerEmail and OwnerPhone are NOT candidate keys.

## Step Two

Break into two relations: OWNER and PET
 * OWNER (OwnerLastName, OwnerFirstName, OwnerPhone, OwnerEmail)
 * PET (PetName, PetType, PetBreed, PetDOB, Foreign Key, Service, date, charge )

FOR OWNER:
 Functional Dependencies:
 * OwnerEmail --> (OwnerLastName, OwnerFirstName, OwnerPhone)
 * OwnerPhone --> (OwnerLastName, OwnerFirstName, OwnerEmail)
 * OWNER Candidate Keys: OwnerPhone, OwnerEmail
Is every determinant a candidate key?

YES OwnerEmail and OwnerPhone are candidate keys Normalization complete!

We can choose either candidate key as primary key.

We can use  OwnerPhone as primary key, THEN:

 * OWNER (OwnerPhone, OwnerLastName, OwnerFirstName, OwnerEmail)
 * PET (PetName, PetType, PetBreed, PetDOB, OwnerPhone,Service, Date, Charge )
Functional Dependencies:
 * PetName --> (PetType, PetBreed, PetDOB, OwnerPhone)
  
PET and Service Candidate Keys: PetName
Is every determinant a candidate key?
No PetName is not a candidate key

### Step Three :

Break Pet into two relation PET and SERVICE
 * OWNER (OwnerPhone, OwnerLastName, OwnerFirstName, OwnerEmail)
 * PET (PetName, PetType, PetBreed, PetDOB, OwnerPhone)
 * SERVICE (PetName, Date, Service, Charge)
PET  Functional Dependencies:
 * PetName --> (PetType, PetBreed, PetDOB, OwnerPhone)
PET Candidate Keys: PetName
Is every determinant a candidate key?
YES PetName is a candidate key Normalization complete!
#### FINAL NORMALIZED REALTIONS:

 * OWNER (OwnerPhone, OwnerLastName, OwnerFirstName, OwnerEmail)
 * PET (PetName, PetType, PetBreed, PetDOB, OwnerPhone)
 * SERVICE (PetName, Date, Service, Charge)  