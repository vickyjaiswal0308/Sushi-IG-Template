### Summary

The Patient Flag is made up of Patient Flag and Provenances resources.  The  Flag resources are linked via a Patient resource. This is modelled here as a contained resource, and as such has no lifetime outside of the constituent Patient Flag resources.

### Data Model

<div class="mermaid">
erDiagram
  Patient {
    NHS-number identifier
  }
  PatientFlag {
    patient Patient
    code CodeableConcept
    category CodeableConcept
    contained Provenance
  }
  Provenance {
    recorded DateTime
    agent Agent
  }

  Patient ||--o| PatientFlag : has

  PatientFlag ||--|| Provenance : contains

