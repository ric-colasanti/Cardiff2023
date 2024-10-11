# Cardiff2023

# Overview

This NetLogo model simulates a healthcare system with caregivers and patients. The model tracks the number of patients, wait time, and average wait time. Caregivers have different services (A, B, C) and patients have requirements that need to be fulfilled.

##  Global Variables

    total-number-of-patients: The total number of patients in the system.
    total-wait-time: The total wait time of all patients.
    average-wait-time: The average wait time of all patients.
    total-processed: The total number of patients processed.


## Breeds

    caregivers: A breed of turtles representing caregivers.
    patients: A breed of turtles representing patients.


## Caregiver Properties

    service: The service provided by the caregiver (A, B, C).
    time: The time it takes for the caregiver to process a patient.
    psubject: The patient currently being processed by the caregiver.
    pcounter: A counter to track the time left for the caregiver to process a patient.


## Patient Properties

    requirements: A list of requirements that need to be fulfilled.
    requirement: The current requirement being fulfilled.
    state: The state of the patient (X, F, n).
    time-in: The time the patient entered the system.
    time-out: The time the patient left the system.


## Patch Properties

    wait-area: A flag indicating whether the patch is a wait area.

# Procedures  

## new-patient

Creates a new patient with a random requirement and moves it to a wait area.
setup

Initializes the model by creating caregivers and patients, setting up the wait areas, and resetting the global variables.
change-patient-state

Changes the state of a patient based on its requirements. If the patient has no more requirements, it is moved to the end of the simulation and its wait time is calculated.
process-patient

Processes a patient by moving it to the caregiver's location and changing its state.
go

The main loop of the simulation. It updates the state of patients and caregivers, processes patients, and creates new patients with a certain probability.
# Notes

    The model uses a simple random number generator to create new patients.
    The model assumes that caregivers can process patients one at a time.
    The model does not account for any conflicts or priorities between caregivers and patients
