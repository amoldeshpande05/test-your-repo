<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
  html,
  div,
  body {
    background-color: #1a1a1a;
    font-family: 'IBM Plex Sans', sans-serif;
    font-size: 18px;
    outline: none;
  }
  body {
    font-family: Helvetica, sans-serif;
  }
  /* The actual timeline (the vertical ruler) */
  .timeline {
    position: relative;
    max-width: 1200px;
    margin: 0 auto;
    margin-left: 50px;
  }
  .content p {
    margin: 0px;
  }
  .content .afterbutton
  {
    padding-top: 16px;
  }
  /* The actual timeline (the vertical ruler) */
  .timeline::after {
    content: '';
    position: absolute;
    width: 1px;
    background-color: white;
    top: 15px;
    bottom: 80px;
    left: 18px;
    margin-left: -2px;
  }
  /* Container around content */
  .container {
    padding: 0px 0px;
    width: 70%;
    align-content: left;
    margin: 0px 0px 0px 0px;
    margin-left: 25px;
    margin-top: 32px;
  }
  /* The circles on the timeline */
  .container::after {
    content: '';
    position: absolute;
    width: 10px;
    height: 10px;
    right: -6px;
    background-color: white;
    border: 0px solid #FF9F55;
    top: 15px;
    border-radius: 50%;
    z-index: 1;
    margin: 0px 0px 0px 0px;
  }
  /* Place the container to the left */
  .left {
    left: 0px;
  }
  /* Place the container to the right */
  .right {
    left: 0px;
  }
  /* Add arrows to the left container (pointing right) */
  .left::before {
    content: " ";
    height: 0;
    top: 22px;
    width: 0;
    z-index: 1;
    right: 30px;
    border: medium solid white;
    border-width: 10px 0 10px 10px;
    border-color: transparent transparent transparent white;
  }
  /* Fix the circle for containers on the right side */
  .right::after {
    left: -13px;
  }
  /* The actual content */
  .content {
    padding: 5px 10px;
    color: white;
    background: transparent;
  }
  .button.is-dark.is-medium {
    font-family: 'IBM Plex Sans', sans-serif;
    background: transparent;
    border-color: white;
    color: #fff;
    border: 1px solid white;
    padding: 10px;
    padding-left: 20px;
    margin-bottom: 13px;
    border-radius: 0px;
    min-width: 180px;
    font-size: 14px;
    text-align: left;
    min-height: 48px;
    margin: 0px;
    justify-content:left;
  }
  .button.is-dark.is-medium:hover {
    font-family: 'IBM Plex Sans', sans-serif;
    background-color: #2a67f5;
    border-color: white;
    color: #fff;
    text-decoration: none;
  }
  .footer {
    display: flex;
    background-color: #343A3E;
    margin-top: 20px;
    padding: 0px;
    max-width: 1200px;
  }
  .github-icon {
    min-height: 100%;
    min-width: 100%;
    object-fit: cover;
    object-position: 250% 100px;
    opacity: 15%;
    bottom: 15px;
  }
  .image-content {
    padding: 5px 10px;
    background: transparent;
    color: black;
    position: absolute;
    font-size: 27px;
  }
  .image-div {
    position: relative;
    background-color: white;
    min-width: 50%;
    background-image: linear-gradient(rgba(255,255,255,0.9), rgba(255,255,255,0.9)), url("https://raw.githubusercontent.com/IBM/Developer-Playground/master/didact/images/github.svg");
    background-position: -50% 60px;
    background-repeat: no-repeat;
    padding-top: 20px;
    padding-left: 20px;
  }
  .image-btn {
    position: absolute;
    right: 0;
    bottom: 0%;
    background-color: #0062FF;
    width: 300px;
    padding: 0px;
    padding-bottom: 20px;
  }
  .image-link span 
  {
    float: right;
    font-size: 32px;
    padding-right: 20px;
  }
  .image-btn .image-link:hover
  {   
    text-decoration: none;
    color: white;
    background-color: #0353E9;
  }
  .image-btn  a:hover
  {
    text-decoration: none;
    color: white;
  }
  .image-link {
    color: white;
    display: block;
    padding: 5px 10px 5px 10px;
    line-height: 28px;
    font-size: 16px;
  }
  .header
  {
    background-image: url('https://github.com/IBM/Developer-Playground/blob/master/didact/images/data-quality.png?raw=true');
    background-position: right;
    width: 95%;
    min-height: 70px;
    display: inline-block;
    margin-top: 20px;
    margin-bottom: 20px;
    margin-left: 30px;
    margin-right: 30px;
    max-width: 1200px;
    background-repeat: no-repeat;
    background-size: 700px 500px;
  }
  .header .left-content
  {
   float: left;
    width: 50%;
    background-color: #525252;
    min-height: 270px;
    font-size: 16px;
  }
  .header .left-content h4
  {
    background: none;
    color: white;
    padding-left: 25px;
    padding-right: 25px;
  }
  .header .left-content div
  {
    background: none;
    color: white;
    padding-left: 15px;
    padding-right: 25px;
    font-size: 16px;
    margin-bottom: 10px;
    margin-top:10px;
  }
  .header .left-content ul
  {
    margin: 0px;
    margin-left: 25px;
    margin-bottom: 10px;
    line-height: 16px;
  }
  .container a
  {
    color: #78A9FF;
    background-color: transparent;
    text-decoration: none;
  }
  .container a:visited
  {
    color: #8C43FC;
    background-color: transparent;
    text-decoration: none;
  }
  .apptitle
  {
    margin-left: 25px;
    margin-top: 20px;
    margin-bottom: 0px;
    font-size: 28px;
    color: white;
  }
  .subheading
  {
    margin-left: 25px;
    margin-top: 0px;
    margin-bottom: 0px;
    font-size: 16px;
    color: #c1c7cd;
  }
  .assetdetails{
    margin-left: 30px;
    padding-bottom: 20px;
    margin-top: 16px;
}
  a:hover{
      color: #A6C8FF;
      text-decoration: underline;
  }
  a:visited{
      color: #BE95FF;
  }
  .description{
    margin-left: 30px;
    margin-top: 16px;
  }
</style>
</head>
<body>
<div class="header">
      <div class="left-content">
          <div class="apptitle" style="font-size: 28px; color: white; padding-top:35px;"> 
    Data Quality for AI
          </div>
          <div class="subheading">
    Assess the quality of data sets for AI models.
          </div>
      </div>
      </div>
   <br>
   <br>
   <div class="description">
        <div>
        Access to quality data can significantly reduce model building time, streamline data preparation efforts, and improve the overall reliability of the AI pipeline.</div>
        <br>
        <div>
            The Data Quality for AI integrated toolkit provides various data profiling and quality estimation metrics to assess the quality of ingested data in a systematic and objective manner. This application allows you to experiment with the Data Quality for AI toolkit to assess the quality of your dataset.        
        </div>
    </div> 
   <br>
   <br>
        <div class="assetdetails">
            <p style="font-size:24px">Learning Resources</p>
            <p><a href="https://developer.ibm.com/learningpaths/data-quality-ai-toolkit/">Get started with Data Quality for AI</a></p>
            <br>
            <p style="font-size: 24px;">Included APIs</p>
            <p><a href="https://developer.ibm.com/apis/catalog/dataquality4ai--data-quality-for-ai/Introduction">Data Quality for AI API</a></p>
            <br>
            <p style="font-size: 24px;">Pre-requisites</p>
            <p>Obtain API credentials:</p>
            <ul>
            <li><a href="https://www.ibm.com/account/reg/us-en/signup?formid=urx-50307">Subscribe  </a> to the Data Quality for AI.</a></li>
            <li>Check your <a href="https://developer.ibm.com/profile/myapis"> API Subscriptions</a>.</li>
            <li>Select the subscription for Data Quality for AI to proceed.</li>
            <li>You can obtain your Client ID/Secret from here. Else, you can "Generate API Key".</li>
            </ul>
            <br>
            <p style="font-size: 24px;">Instructions</p>
            <p>Please follow all the below steps in proper sequence.</p>
        </div>

   <div class="timeline">
      <div class="container right" style="margin-top:0px;padding-top:0px;">
         <div class="content">
            <p>Clone the GitHub repository.</p>
            <a class="button is-dark is-medium" title="Get the Code" href="didact://?commandId=extension.sendToTerminal&text=data-quality%7Cget-code%7Cdata-quality|git%20clone%20-b%20DART%20https://github.com/IBM/Developer-Playground.git%20${CHE_PROJECTS_ROOT}/data-quality/">Get Code</a>
         </div>
      </div>
      <div class="container right">
         <div class="content">
            <p>Install required dependencies for executing application.</p>
            <a class="button is-dark is-medium" title="Build the Application" href="didact://?commandId=extension.sendToTerminal&text=data-quality%7Cbuild-application%7Cdata-quality|cd%20${CHE_PROJECTS_ROOT}/data-quality/DataQuality%20%26%26%20npm%20install%20--production">Install Dependencies</a>
         </div>
      </div>
      <div class="container right">
         <div class="content">
            <p>Configure the application. See pre-requisites.</p>
            <a class="button is-dark is-medium" title="Open the File" href="didact://?commandId=extension.openFile&text=data-quality%7Cconfigure-application%7C${CHE_PROJECTS_ROOT}/data-quality/DataQuality/.env">Configure Application</a>
         </div>
      </div>
      <div class="container right">
         <div class="content">
            <p>Launch the application in the preview window.</p>
            <a class="button is-dark is-medium" title="Launch the Application" href="didact://?commandId=extension.sendToTerminal&text=data-quality%7Claunch-application%7Cdata-quality|cd%20${CHE_PROJECTS_ROOT}/data-quality/DataQuality%20%26%26%20node%20server.js">Launch Application</a>
         </div>
      </div>
   </div>
   <br>
   <div class="footer" style="margin-left:30px;">
      <div class="content" style="padding:30px;padding-left:60px;margin-right:80px;padding-bottom:0px;">
         <p>To edit or explore the application, make sure to stop it first.</p>
         <a class="button is-dark is-medium" title="Stop Application" href="didact://?commandId=vscode.didact.sendNamedTerminalCtrlC&text=data-quality" >Stop Application</a>
         <p class="afterbutton">Explore and update the code as per your requirement.</p>
         <a class="button is-dark is-medium" title="Explore the Code" href="didact://?commandId=extension.openFile&text=data-quality%7Cexplore-code%7C${CHE_PROJECTS_ROOT}/data-quality/DataQuality/src/App.js">Explore Code</a>
         <p class="afterbutton ">Re-launch the application to view the changes made.</p>
         <a class="button is-dark is-medium" title="Re-Launch the Application" href="didact://?commandId=extension.sendToTerminal&text=data-quality%7Crelaunch-application%7Cdata-quality|cd%20${CHE_PROJECTS_ROOT}/data-quality/DataQuality%20%26%26%20npm%20install%20--only=dev%20%26%26%20rm%20-rf%20build%20%26%26%20npm%20run%20build%20%26%26%20node%20server.js">Re-Launch Application</a>
      </div>
      <div class="image-div">
         <p class="image-content">Want to explore this project more?
            <span style="font-size:15px;margin-top:0px;display:block;">Head over to the <a href="https://github.com/IBM/Developer-Playground/tree/DART" target="_blank">Github Repository</a></span>
            <span style="font-size:15px;margin-top:0px;display:block;">For further assistance reach out to <a href="https://github.com/IBM/Technology-Sandbox-Support/issues/new/choose" target="_blank"> Help & Support</a></span>
            <span style="font-size:15px;margin-top:0px;display:block;">Check out our <a href="https://ibm.github.io/Technology-Sandbox-Support/" target="_blank"> FAQs</a></span>
         </p>
         <div class="image-btn">
            <a class="image-link" href="didact://?commandId=extension.openURL&text=data-quality%7Cview-product-details%7Chttps://www.ibm.com/products/dqaiapi
               " target="_blank">
               View Product Details 
               <span>
                  <svg style="position: absolute; right: 10px;" fill="#ffffff" focusable="false" preserveAspectRatio="xMidYMid meet" xmlns="http://www.w3.org/2000/  svg" width="25" height="25" viewBox="0 0 32 32" aria-hidden="true">
                     <path d="M18 6L16.6 7.4 24.1 15 3 15 3 17 24.1 17 16.6 24.6 18 26 28 16z"></path>
                     <title>Arrow right</title>
                  </svg>
               </span>
            </a>
            <a class="image-link" href="didact://?commandId=extension.openURL&text=data-quality%7Cget-trial-subscription%7Chttps://www.ibm.com/account/reg/us-en/signup?formid=urx-50307" target="_blank">
               Get Trial Subscription 
               <span>
                  <svg style="position: absolute; right: 10px;" fill="#ffffff" focusable="false" preserveAspectRatio="xMidYMid meet" xmlns="http://www.w3.org/2000/  svg" width="25" height="25" viewBox="0 0 32 32" aria-hidden="true">
                     <path d="M18 6L16.6 7.4 24.1 15 3 15 3 17 24.1 17 16.6 24.6 18 26 28 16z"></path>
                     <title>Arrow right</title>
                  </svg>
               </span>
            </a>
         </div>
      </div>
   </div>
   <br><br>
</body>
</html>
