
let form = document.querySelector("form");
form.addEventListener('submit', (e) => {
  e.preventDefault();
  document.querySelector("#sub").value = "Submiting..";
  let data = new FormData(form);
  fetch('https://script.google.com/macros/s/AKfycbwWMi-U1Ybnj87f23jSrLwDsJ4P_d6xZx-uL4zSpeQYD1lKoYfNtcEahpqFxnNmbVfW/exec', {
    method: "POST",
    body: data

  })
    .then(res => res.text())
    .then(data => {
      alert(data);
      document.querySelector("#sub").value = "Submit"
      form.reset();
    });
});


const api_url =
  "https://script.google.com/macros/s/AKfycbwWMi-U1Ybnj87f23jSrLwDsJ4P_d6xZx-uL4zSpeQYD1lKoYfNtcEahpqFxnNmbVfW/exec";

// Defining async function
async function classapi(url) {

  // Storing response
  const response = await fetch(url);

  // Storing data in form of JSON
  var data = await response.json();

  classdatashow(data);
}

// Defining async function


// Calling that async function
classapi(api_url);


// Function to define innerHTML for HTML table
function classdatashow(data) {
  console.log(data);
  let tab =
    ``;


  // Loop to access all rows
  for (let r of data.content) {
    tab += `
   
                <div class="col-md-4">
          <div class="card mb-4 box-shadow">
            <img class="card-img-top"
              src="${r[4]}" height="150px"
              alt="Card image cap">
            <div class="card-body">
              <h5 class="card-title">${r[2]}</h5>
              
    <h6 class="card-subtitle mb-2 text-muted">${r[5]}</h6>
              <p class="card-text d-vertical overflow-auto">${r[3]}</p>
              <div class="d-flex justify-content-between align-items-center">
                <div class="btn-group">
                 <button type="button" class="btn btn-primary" data-toggle="modal" data-target="#joinus">
          Join Us
        </button>
                  
                </div>
                <small class="text-muted">Podcast Id:- ${r[0].slice(0, 10)}</small>
              </div>
            </div>
          </div>
        </div>
    `;
  }
  // Setting innerHTML as tab variable
  document.querySelector("#datafetch").innerHTML = tab;
};
