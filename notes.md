rails generate resource doctor name:string department:string --no-test-framework
Associations:
Doctor
  has_many :patients
  has_many :appointments

rails generate resource patient name:string age:integer --no-test-framework
Patient
  has_many :doctors
  has_many :appointments

rails generate resource appointment appointment_datetime:datetime doctor:doctor_id, patient:patient_id --no-test-framework

Table:
appointments
belongs_to :doctor
belongs_to :appointment
- appointment_datetime:datetime

Doctor -< Appointment >- Patient
----------

Create a Doctor#index page that displays each doctor's name, a link to their show page, and a count of their patients.

Create a Doctor#show page that displays the doctor's name, department, and appointments, with each appointment's date, time, and patient name (linking to the patient's show page).

Create a Patient#show page that lists the date and time for each of their appointments and links to the corresponding doctor's show page.

Create a Patient#index page that displays a link to each patient's show page and the total number of appointments they have.

Create an Appointment#show page that shows the date, time, patient, and doctor for that particular appointment. Note that there should NOT be an Appointment#index page –– we don't want to have all of the appointments on display for anyone to see.


doctor index page:
each doctor's name, a link to their show page, and a count of their patients.
