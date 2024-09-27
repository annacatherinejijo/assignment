--STEP 1

SELECT *
FROM crime_scene_report
WHERE type = 'murder'
AND city = 'SQL City'
AND date = 20180115

--STEP 2

SELECT *
FROM person
WHERE address_street_name = 'Northwestern Dr'
ORDER BY address_number DESC
LIMIT 1

--STEP 3

SELECT *
FROM person
WHERE address_street_name = 'Franklin Ave'
LIMIT 10

--STEP 4

SELECT *
FROM person
WHERE address_street_name = 'Franklin Ave'
AND name LIKE '%Annabel%'
LIMIT 10

--STEP 5

SELECT *
FROM interview
WHERE person_id IN (14887,16371) 
LIMIT 10

--STEP 6

SELECT *
FROM drivers_license
WHERE plate_number LIKE '%H42W%'
LIMIT 10

--STEP 7

SELECT p. *
FROM drivers_license as d1
INNER JOIN person as p on d1.id = p.license_id
WHERE plate_number LIKE '%H42W%'
LIMIT 10

--STEP 8

SELECT p. *
FROM drivers_license as d1
INNER JOIN person as p on d1.id = p.license_id
INNER JOIN get_fit_now_member as gf on p.id = gf.person_id
WHERE plate_number LIKE '%H42W%'
LIMIT 10

--STEP 9

SELECT p. * , gf.*
FROM drivers_license as d1
INNER JOIN person as p on d1.id = p.license_id
LEFT JOIN get_fit_now_member as gf on p.id = gf.person_id
WHERE plate_number LIKE '%H42W%'
LIMIT 10

--STEP 10

SELECT p. * , ci.*
FROM drivers_license as d1
INNER JOIN person as p on d1.id = p.license_id
INNER JOIN get_fit_now_member as gf on p.id = gf.person_id
INNER JOIN get_fit_now_check_in as ci on gf.id = ci.membership_id
WHERE plate_number LIKE '%H42W%'
AND membership_status = 'gold'
LIMIT 10

--STEP 11

SELECT p. * , ci.*
FROM drivers_license as d1
INNER JOIN person as p on d1.id = p.license_id
INNER JOIN get_fit_now_member as gf on p.id = gf.person_id
INNER JOIN get_fit_now_check_in as ci on gf.id = ci.membership_id
WHERE plate_number LIKE '%H42W%'
AND membership_status = 'gold'
AND check_in_date = 20180109
LIMIT 10

--STEP 12
<img width="440" alt="image" src="https://github.com/user-attachments/assets/c7863c5d-0575-45fd-baa0-68d532c3ac11">

--STEP 13

SELECT p.*, fb.*
FROM drivers_license as dl
INNER JOIN person as p on dl.id = p.license_id
INNER JOIN facebook_event_checkin as fb on fb.person_id = p.id
WHERE hair_color = 'red'
AND height >= 65
AND height <= 67
AND car_make = 'Tesla'
And car_model = 'Model S'
AND gender = 'female'
LIMIT 100

<img width="419" alt="image" src="https://github.com/user-attachments/assets/cfe26274-95ca-4cf5-99ae-e7af9edd732f">
