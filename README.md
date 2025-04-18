//API

const URL="https://catfact.ninja/facts";

let promise=fetch(URL);
console.log(promise);

const getFacts=async()=>{
    console.log("getting data ....");
    let response=await fetch(URL);
    console.log(response);
}

//JSON

const URLs="https://catfact.ninja/facts";
const factPara=document.querySelector("#fact");
const button=document.querySelector("#button");

const getFact=async()=>{
    console.log("getting data ....");
    let response=await fetch(URLs);
    console.log(response);
    let result=await response.json();
    console.log(result);
    let randomFact=result.data[0].fact;
    factPara.innerText=randomFact;
};

button.addEventListener("click",getFact);


