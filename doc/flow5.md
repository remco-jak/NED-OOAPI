# Flow 5: Result information (students)

# Proposal : THIS IS FOR DISCUSSION ONLY. NOT FINAL


## Flow 5.1 : Return attendance and results

### Sequence diagram 
```mermaid
sequenceDiagram
    participant SIS
    participant Toetsplanning

    loop for each exam/test
        loop for each student / teacher
          Toetsplanning-->>SIS: Send detailed results for this exam for this student
          activate SIS
          Note right of SIS: endpoint /a/ooapi/geenidee/{geenideeId}/students/{geenideeId} (PUT)
          SIS-->>Toetsplanning: 200 - Bedankt!
          deactivate SIS
        end
    end

```

Welke toets scenarios willen we hier kunnen ondervangen. 
We sturen de informatie die ontvangen is vanuit het examensysteem terug richting het KRD.
De vraag is wat is de plek waar je het resultaat op terug wilt schrijven.

Je hebt hiervoor een haak nodig die in het SIS bestaat. Er zou een endpoint voorhanden moeten zijn binnen het SIS waar het KRD naartoe kan schrijven. 

Wat weet het planningssysteem? Het resultaat, de association, de offering waar de association opgedaan is, het component (ID) waar de offering van is afgeleid en de student

Wat heeft het SIS de student, de component 
