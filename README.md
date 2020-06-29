**Pay with Knoma** allows students to checkout via your (the partner) to apply for a zero-interest, fee-free loan from [Knoma](knoma.io/partners). This can be all implemented right into your website so the student never leaves your site. 

This repo is a publically available source code of our [live checkout example](https://knoma-other.herokuapp.com/checkout.html?k-course=TESTCOURSEID) which can be just dropped right into your website as-is*. Alternatively, you can also just use this as a boilerplate and build upon it how you see fit. You are even free to add other payment solutions such as Paypal, or Direct Debit into this template, but if you do do this we ask that Knoma is prioritised. We also suggest keeping the same Knoma related marketing assets as this is important to help the student decide to checkout with Knoma. 

This example is designed to be dynamic, meaning the page content and course within the checkout will change when based on the ID sent via the `k-course` URL parameter. 

###How it Works
The Knoma SDK automatically parses the `k-course` parameter you send within the URL, it will then attempt to find that course ID within our system. If it finds it then the course information is populated into predefined DOM elements, similarly to how scraping works. Additionally, the `k-paywith-action` **DOM** element is also populated with the relevant Course ID. 

###Getting Started
To get started you will first need a `provider-id`. If you do not have this please contact us. Next, please clone this repo and open this in your preffered text editor and replace the "[Provider ID]" (line 47) with your specific provider ID. Following that you are free to customise this as much or as little as you like (following the guidelines listed above). Once you are done please upload this code to a directory where you want the checkout to be hosted. **And that's it!**

###DOM Injected Course Information
Course information can be populated on the page automatically, this is already demonstrated in the live example and subsiqently, the source code. But we have additional support for information such as course description and prerequsits. 

DOM ID | Description
--- | --- | ---
`k-reference` | Course Unique ID/Reference
`k-name` | Course Name
`k-provider` | Provider/School Name
`k-price` | Total Price of Course (with Currency Symbol)
`k-description` | Course Unique ID/Reference
`k-school` | Name of School/Provider
`k-logo` | Logo of School/Provider
`k-prerequisites` | Prerequisites of Course
`k-category` | Knoma Category Type of Course
`k-commitment` | Full-time/Part-time Commitment Type

###Handling Errors
There maybe a case where the course ID sent is invalid. With this we will be unable to return the course information or populate the checkout button with the right Course ID. With this we suggest handling this error using our `pwk` callback function. Again, an example of this can be found in the source code (line 19)

A list of returned errors and other supported callback fuctions along with everything else, including information about course scraping (which is required) can be found in our official [Knoma SDK Documentation](https://www.knoma.io/developer/paywith).  
