# NACH (National Automated Clearing House)

NACH is a web-based and automated procedure platform which was created by NPCI (National payments corporation of India) in 2016 to facilitate funds clearing.

NACH Credit and NACH Debit are electronic systems for handling high-volume, recurring interbank transactions, whether they involve high or low amounts of money.

Its aim is to facilitate high volume transactions.


## Objective of NACH

The main objective of NACH are as follow:

* Supports Mobile-based and Aadhaar-based Automated clearing house transactions.
* It operates as a centralised system for multiple ECS systems.
* It is capable of managing large number of repetitive transactions
* The Regulations to be followed by the user are easy to comprehend and follow.

## Workflow of eNACH

NACH (National Automated Clearing House) is a simpler and faster process of automated  bulk transactions.

Here is steps of NACH how it works:

**Step 1:** Mandates initiation by the Customer to the Corporate.

**Step 2:** Corporate update the progress and send it to the Sponsor Bank.

**Step 3:** At the Sponsor Bank office all mandates are updated and sent to the NPCI.


**Step 4:** NPCI scanned the mandated images and generated the UMRN then to the Destination Bank via NPCI with UMRN No.


**Step 5:** Destination Bank firstly checks the details given by the NPCI if details matched then it sends the verification mandates to the customer and updates the records.

**Step 6** If the Customer accepts the request then the Destination Bank shares the response approved.

**Step 7** NPCI save and update the details then share the response to the Sponsor Bank.

**Step 8** Sponsor Bank share the response Verified customer  to the Corporate


**Step 9** If Customer reject the request the the Destination Bank share the response eMandate not recognized by the customer to the NPCI

**Step 10** NPCI share the response eMandate not recognized by customer to the Sponsor bank 

**Step 11** Sponsor Bank shares the response Invalid user to the Corporate.


~~~
eNACH Process {
   customer.style: {


       stroke: red
      
       stroke-dash: 0
    
     }


     corporate.style: {


       stroke: blue
    
       stroke-dash: 0
    
     }


     Sponsor Bank.style: {


       stroke: orange
    
       stroke-dash: 0
    
     }


     NPCI.style: {


       stroke: maroon
    
       stroke-dash: 0
    
     }


     Destination Bank.style: {


       stroke: green
    
       stroke-dash: 0
    
     }
shape: sequence_diagram


customer: { shape: person }


customer ->corporate : fill all mandate {
   style.animated: true
}


corporate -> Sponsor Bank: Update mandate {
   style.animated: true
}
Sponsor Bank-> NPCI: Scan mandate and generate UMRN {
   style.animated: true
}
NPCI-> Destination Bank: Update with UMRN no. {
   style.animated: true
}
Destination Bank->customer:Match customer details and sent mandate sms to the customer with UMRN {
   style.stroke:orange
   style.animated: true
}
customer-> Destination Bank: Accepted {
   style.stroke:green
   style.animated: true
}
Destination Bank-> NPCI:Response Approved {
   style.stroke:green
   style.animated: true
}
NPCI->Sponsor Bank:Save & Update {
   style.stroke:green
   style.animated: true
}
Sponsor Bank-> corporate:Verified customer {
   style.stroke:green
   style.animated: true
}


customer->Destination Bank:Rejected {
   style.stroke:red
   style.animated: true
}
Destination Bank-> NPCI: Not recornized by customer {
   style.stroke:red
   style.animated: true
}
NPCI-> Sponsor Bank:Invalid Mandate {
   style.stroke:red
   style.animated: true
}
Sponsor Bank-> corporate:Invaild Mandate {
   style.stroke:red
   style.animated: true
}
}
~~~

![Alt text](n1.png)


![Alt text](n2.png)


## E-mandate through Debit card authentication - Process flow



~~~
E-mandate through Debit card authentication - Process flow: {
shape: sequence_diagram
customer: { shape: person }
customer.style: {

    stroke: red
    
    stroke-dash: 0
  
  }

  Corporate.style: {

    stroke: blue
    
    stroke-dash: 0
  
  }

  eNACH API interface.style: {

    stroke: maroon
    
    stroke-dash: 0
  
  }

  Internet Banking Page.style: {

    stroke: orange
    
    stroke-dash: 0
  
  }

  Destination Bank.style: {

    stroke: green
    
    stroke-dash: 0
  
  }

  

Customer->Corporate:1 Mandate initiation {
    style.animated: true
}

Corporate -> eNACH API interface:2 Mandate request to API system {
    style.animated: true
}

eNACH API interface->Internet Banking Page:Redirect {
    style.animated: true
}
Customer->Internet Banking Page: Authentication using Debit card details and OTP. {
    style.animated: true
    style.stroke:green
}
Internet Banking Page->Destination Bank:CBS validation request {
    style.animated: true
}
Destination Bank-> Internet Banking Page: Validation status {
    style.animated: true
    style.stroke:green
}

Internet Banking Page->eNACH API interface:Mandate authorization status {
    style.animated: true
    style.stroke:green
}

eNACH API interface->Corporate:Acceptance/Reject status {
    style.animated: true
    style.stroke:green
}

}
~~~








