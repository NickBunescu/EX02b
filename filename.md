# Step 1


## PETANDOWNER (PetName, PetType, PetBreed, PetDOB, OwnerLastName, OwnerFirstName, OwnerPhone, OwnerEmail)


## Functional Dependencies

##### PetName  (PetType, PetBreed, PetDOB, OwnerLastName, OwnerFirstName, OwnerPhone, OwnerEmail)
##### OwnerEmail  (OwnerLastName, OwnerFirstName, OwnerPhone)
##### OwnerPhone  (OwnerLastName, OwnerFirstName, OwnerEmail)
##### PETANDOWNER Candidate Keys: PetName
##### OwnerEmail and OwnerPhone are not candidate keys

# Step 2

## This can be broken in to OWNER AND PET

###### OWNER (OwnerLastName, OwnerFirstName, OwnerPhone, OwnerEmail)
##### PET (PetName, PetType, PetBreed, PetDOB)

## OWNER functional dependencies:
##### OwnerEmail  (OwnerLastName, OwnerFirstName, OwnerPhone)
##### OwnerPhone  (OwnerLastName, OwnerFirstName, OwnerEmail)
##### OWNER Candidate Keys: OwnerPhone, OwnerEmail 
##### Both OwnerPhone, and OwnerEmail are candidate keys after normalization

##### We can choose either candidate key as primary key

## Now if we use OwnerPhone as primary key, we will have:
##### OWNER (OwnerPhone, OwnerLastName, OwnerFirstName, OwnerEmail)
##### PET (PetName, PetType, PetBreed, PetDOB, OwnerPhone)

## Functional Dependencies:
##### PetName(PetType, PetBreed, PetDOB, OwnerPhone)

## PET Candidate Keys: PetName
##### We can do the same with OwnerEmail as we did for OwnerPhone

## We will get:
##### OWNER (OwnerPhone, OwnerLastName, OwnerFirstName, OwnerEmail)
##### PET (PetName, PetType, PetBreed, PetDOB, OwnerEmail)

## Final normalization relation:
##### OWNER (OwnerPhone, OwnerLastName, OwnerFirstName, OwnerEmail)
##### PET (PetName, PetType, PetBreed, PetDOB, OwnerEmail)
