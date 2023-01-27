Common Element: Nav with 3 links: 1.Home, 2.Owners, 3.Pets
1.HOME -- links to the main landing page of the vet office

2. OWNERS INDEX -- links to an index UL of OWNERS where each li is clickable and connects to the OWNER show-page

3. PETS INDEX -- Links to an index UL of pets where each clickable li connects to the PET show-page

OWNER DETAILS -- displays OWNER info name, address, phone, email and PET names -- PET names on OWNER show-page connect to a PET show-page

PET DETAILS -- displays PET info in OL li's, including a photo of the PET, name, age, sex etc... see entities of PET for more details.
Also displays OWNER name which comes through via ref using the foreign key owner_id -- this li is clickable to connect to the OWNER show-page.

---

ENTITIES -- diagram in img.

OWNER
id - serial primary key (foreign key in pet as owner_id)
name - varchar(100) NOT NULL
address - text NOT NULL
phone - varchar (11)
email - varchar(100)
pets - array (of pet ids) -- (one owner can have many pets)

PET
id - serial primary key (used as foreign key in owner's array of pets)
name - varchar(100) NOT NULL
age - int NOT NULL
sex - varchar(1) M/F NOT NULL
type - varchar(100) e.g., dog, cat, bird etc.
breed - varchar(100) e.g., chihuahua, siamese, cockatoo
photo - not sure how imgs are handled in databases other than urls which im not sure is applicable here?
condition - text (null if new pet, this field gets filed by the vet)
owner_id - INT (foreign key from owner.id) -- (there is only one owner id)
