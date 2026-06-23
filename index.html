<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>AI XAUUSD Dashboard</title>

<style>
body{
margin:0;
background:#0b0f1a;
color:white;
font-family:Arial;
}

#chart{
height:60vh;
}

.panel{
padding:15px;
background:#111827;
}

.signal{
font-size:24px;
font-weight:bold;
margin-bottom:15px;
}

.buy{
color:#00ff88;
}

.sell{
color:#ff4d4d;
}

.neutral{
color:#ffd166;
}

.info{
white-space:pre-line;
font-size:14px;
}
</style>
</head>

<body>

<div id="chart"></div>

<div class="panel">
<h2>🤖 AI Technical Analyzer XAUUSD</h2>

<div id="signal" class="signal">
LOADING...
</div>

<div id="desc" class="info"></div>
</div>

<script src="https://s3.tradingview.com/tv.js"></script>

<script>
new TradingView.widget({
container_id:"chart",
symbol:"OANDA:XAUUSD",
interval:"15",
theme:"dark",
style:"1",
locale:"en",
autosize:true
});
</script>

<script>

const API_KEY = "d7b638440aff48d39890384f6787f28a";

async function analyze(){

try{

const response = await fetch(
`https://api.twelvedata.com/time_series?symbol=XAU/USD&interval=1min&outputsize=50&apikey=${API_KEY}`
);

const data = await response.json();

if(!data.values){
document.getElementById("signal").innerText="DATA ERROR";
document.getElementById("desc").innerText=JSON.stringify(data);
return;
}

let closes = data.values
.map(v=>parseFloat(v.close))
.reverse();

function EMA(period,array){

let k=2/(period+1);
let ema=array[0];

for(let i=1;i<array.length;i++){
ema=array[i]*k+ema*(1-k);
}

return ema;
}

function RSI(array){

let gain=0;
let loss=0;

for(let i=1;i<array.length;i++){

let diff=array[i]-array[i-1];

if(diff>0){
gain+=diff;
}
else{
loss+=Math.abs(diff);
}
}

let rs=gain/(loss||1);

return 100-(100/(1+rs));
}

let lastPrice=closes[closes.length-1];

let ema20=EMA(20,closes);
let ema50=EMA(50,closes);
let rsi=RSI(closes);

let signal="";
let desc="";
let css="";

if(ema20>ema50 && rsi>55){

signal="🟢 BUY BIAS";
css="buy";

desc=
`Trend : Bullish

Price : ${lastPrice}

EMA20 : ${ema20.toFixed(2)}
EMA50 : ${ema50.toFixed(2)}
RSI : ${rsi.toFixed(2)}

Advice :
Cari pullback untuk entry buy.`;

}

else if(ema20<ema50 && rsi<45){

signal="🔴 SELL BIAS";
css="sell";

desc=
`Trend : Bearish

Price : ${lastPrice}

EMA20 : ${ema20.toFixed(2)}
EMA50 : ${ema50.toFixed(2)}
RSI : ${rsi.toFixed(2)}

Advice :
Cari rejection resistance untuk entry sell.`;

}

else{

signal="⚪ NO TRADE";
css="neutral";

desc=
`Trend : Sideways

Price : ${lastPrice}

EMA20 : ${ema20.toFixed(2)}
EMA50 : ${ema50.toFixed(2)}
RSI : ${rsi.toFixed(2)}

Advice :
Tunggu breakout yang jelas.`;

}

document.getElementById("signal").innerText=signal;
document.getElementById("signal").className="signal "+css;

document.getElementById("desc").innerText=desc;

}
catch(err){

document.getElementById("signal").innerText="ERROR";
document.getElementById("desc").innerText=err.message;

}

}

analyze();

setInterval(analyze,30000);

</script>

</body>
</html>
