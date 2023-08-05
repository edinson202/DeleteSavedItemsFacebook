# DeleteSavedItemsFacebook

// Returns a Promise that resolves after "ms" Milliseconds
const timer = ms => new Promise(res => setTimeout(res, ms))

async function load1 () { // We need to wrap the loop into an async function for this to work
  var links = Array.from(document.querySelector('[role=main]').querySelectorAll('[aria-label="Más"]')).slice(1)

  for (var i = 0; i < links.length; i++) {
    console.log("A: " + i);
    links[i].click();
    await timer(100); // then the created Promise can be awaited
  }
}


async function load2 () { // We need to wrap the loop into an async function for this to work
  var links = Array.from(document.querySelectorAll('[role=menuitem]'))
  
  for (var i = 0; i < links.length; i++) {
    console.log("B: " + i);
    links[i].click();
    await timer(100); // then the created Promise can be awaited
  }
}


// ------------------
while(true){
  await load1();
  await load2();
  await timer(100); // then the created Promise can be awaited
}
 





