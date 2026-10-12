[index.html](https://github.com/user-attachments/files/33341375/index.html)
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SaltLab Café · Gestión</title>
<style>
:root{--ink:#41316f;--purple:#eee5ff;--pink:#ffd7e8;--cream:#fff8ec;--teal:#078b83;--orange:#bd6500;--line:#bfb0df}
*{box-sizing:border-box}body{margin:0;color:var(--ink);font-family:ui-rounded,"Trebuchet MS",system-ui,sans-serif;background:linear-gradient(#ffd7e8 0 43%,#d8e5ff 43% 65%,#c6f3e8 65%);min-height:100vh;font-weight:700}
header{height:76px;background:#fff4fa;border-bottom:5px solid var(--ink);box-shadow:0 4px 0 #a8dcd4;display:flex;align-items:center;justify-content:space-between;padding:8px 16px;gap:12px;position:sticky;top:0;z-index:5}
.brand{display:flex;align-items:center;gap:12px;min-width:245px}.logo{width:48px;height:48px;border-radius:50%;background:linear-gradient(135deg,#ffcf69,#53cfc0);border:3px solid var(--ink);display:grid;place-items:center;font-size:23px;box-shadow:3px 3px 0 var(--ink)}.brand h1{font-size:18px;margin:0}.brand small{font-size:10px;letter-spacing:2px;color:#078b83}
nav{display:flex;flex-wrap:wrap;justify-content:center;gap:5px;background:var(--purple);border:3px solid var(--ink);border-radius:18px;padding:5px}
button,.navbtn{font:inherit;cursor:pointer;color:var(--ink);border:2px solid var(--ink);border-radius:13px;background:#e8dcff;padding:8px 12px;box-shadow:2px 3px 0 var(--ink);transition:.12s}
button:hover,.navbtn:hover{transform:translateY(-1px);filter:brightness(1.03)}button:active{transform:translate(2px,2px);box-shadow:none}.navbtn.active,.pill.active{background:#ffe58c}
.profile{text-align:right;white-space:nowrap;font-size:13px}.profile small{display:block;color:var(--teal);font-size:11px;margin-top:3px}
main{display:grid;grid-template-columns:minmax(0,2.05fr) minmax(330px,1fr) 180px;gap:18px;padding:24px 18px 55px;max-width:1800px;margin:auto}
.panel{background:var(--purple);border:4px solid var(--ink);border-radius:20px;box-shadow:5px 6px 0 var(--ink);padding:14px;min-width:0}
.search{width:100%;border:3px solid var(--ink);border-radius:15px;padding:13px 15px;font:inherit;font-weight:500;font-size:15px;color:var(--ink);background:#fffdf9;margin-bottom:10px}
.filters{display:flex;flex-wrap:wrap;gap:6px;margin-bottom:14px}.pill{padding:5px 10px;border-radius:18px;font-size:12px}
.group{border-top:3px solid var(--line);padding-top:9px;margin-top:9px}.group-title{font-size:10px;letter-spacing:.7px;color:#8172b0;margin:0 0 8px 4px}.products{display:grid;grid-template-columns:repeat(4,minmax(0,1fr));gap:7px}
.product{display:flex;align-items:center;gap:8px;text-align:left;padding:5px;border-radius:12px;background:#fffdf8;min-width:0;font-size:12px;line-height:1.25}.emoji{width:34px;height:34px;flex:0 0 34px;border:2px solid var(--ink);border-radius:10px;background:#d3f5eb;display:grid;place-items:center;font-size:20px}.product strong{display:block;overflow-wrap:anywhere}.price{color:var(--orange);display:block;margin-top:2px}
.ticket{background:var(--cream);align-self:start}.ticket h2{font-size:17px;margin:2px 0 14px}.empty{text-align:center;padding:38px 0;color:#9282bc;font-size:13px}.empty span{display:block;font-size:34px;margin-bottom:8px}.ticket-items{max-height:250px;overflow:auto}.ticket-row{display:flex;align-items:center;justify-content:space-between;gap:8px;padding:8px 0;border-bottom:1px dashed #c9bcd9;font-size:13px}.ticket-row button{padding:1px 7px;box-shadow:none;border-radius:8px;margin-left:6px}.label{display:block;color:#8a78b6;font-size:11px;margin:10px 0 6px}.ticket select{width:100%;padding:12px;border:3px solid var(--ink);border-radius:15px;background:#fff;font:inherit;color:var(--ink)}.totals{border-top:2px dashed #c9bcd9;margin-top:12px;padding-top:8px;font-size:13px}.total-line{display:flex;justify-content:space-between;margin:8px 0}.grand{font-size:27px;color:var(--teal);font-weight:900}.charge{width:100%;border-radius:28px;background:#ffd5e3;margin-top:10px;padding:13px;color:#9a8caf;border:3px solid #b8a0bd;box-shadow:none}.charge.ready{background:#ffe58c;color:var(--ink);border-color:var(--ink);box-shadow:2px 3px 0 var(--ink)}
.service{background:#ffd8e8;border:3px solid var(--ink);border-radius:17px;padding:10px;height:max-content;font-size:11px}.service h3{font-size:11px;margin:0 0 12px}.worker{background:#fff8ec;border:2px solid var(--ink);border-radius:16px;padding:10px;margin-top:8px;display:flex;gap:8px;align-items:center}.avatar{width:34px;height:34px;border-radius:50%;display:grid;place-items:center;background:#a4e8dc;border:2px solid var(--ink);font-size:19px}.worker small{display:block;color:#8b7ab4;margin-top:3px}.timer{color:#e45f43;margin-top:2px;font-family:monospace}
footer{text-align:center;font-size:11px;padding:12px;color:var(--ink);border-top:3px solid var(--ink);background:#c5f0e5}
.notice{position:fixed;bottom:20px;right:20px;background:#fff8ec;border:3px solid var(--ink);border-radius:14px;padding:12px 18px;box-shadow:4px 4px 0 var(--ink);display:none;z-index:9}
@media(max-width:1150px){header{height:auto;flex-wrap:wrap}.brand{min-width:0}nav{order:3;width:100%}main{grid-template-columns:minmax(0,1.5fr) minmax(300px,1fr)}.service{grid-column:1/-1}.products{grid-template-columns:repeat(3,minmax(0,1fr))}}
@media(max-width:700px){main{grid-template-columns:1fr;padding:12px}.profile{margin-left:auto}.products{grid-template-columns:repeat(2,minmax(0,1fr))}.panel{padding:10px}nav .navbtn{font-size:11px;padding:7px}header{padding:8px}.brand h1{font-size:15px}}
</style>
</head>
<body>
<header>
 <div class="brand"><div class="logo">🌴</div><div><h1>SaltLab Café</h1><small>FLAVOR MEETS THE SEA</small></div></div>
 <nav id="nav"><button class="navbtn active" data-page="Calculadora">▦ Calculadora</button><button class="navbtn" data-page="Fichaje">◴ Fichaje</button><button class="navbtn" data-page="Ventas">◴ Ventas</button><button class="navbtn" data-page="LSPD">♙ LSPD</button><button class="navbtn" data-page="Taxis">🚕 Taxis</button><button class="navbtn" data-page="EMS">♡ EMS</button><button class="navbtn" data-page="Jefe">♢ Jefe</button></nav>
 <div class="profile">Noa Flores<small>● Sesión activa</small></div>
</header>
<main>
<section class="panel">
 <input class="search" id="search" placeholder="⌕  Buscar producto..." aria-label="Buscar producto">
 <div class="filters" id="filters"></div><div id="catalog"></div>
</section>
<section class="panel ticket">
 <h2>🧾 Ticket</h2><div id="ticketItems" class="ticket-items"><div class="empty"><span>🧺</span>Añade productos para empezar.</div></div>
 <label class="label" for="agreement">♧ CONVENIO</label><select id="agreement"><option value="0">Sin convenio</option><option value="5">Convenio · 5% descuento</option><option value="10">Convenio · 10% descuento</option><option value="15">Convenio · 15% descuento</option></select>
 <div class="totals"><div class="total-line"><span>Subtotal</span><span id="subtotal">0,00 $</span></div><div class="total-line" style="color:#bd6500"><span>Descuento</span><span id="discount">−0,00 $</span></div><div class="total-line" style="align-items:center"><span>Total</span><span class="grand" id="total">0,00 $</span></div></div>
 <button class="charge" id="charge" disabled>▣ Cobrar</button>
</section>
<aside class="service"><h3>🟢 DE SERVICIO <span style="float:right;background:white;border-radius:50%;padding:2px 7px">1</span></h3><div class="worker"><div class="avatar">👩🏻</div><div>Kiana Brooks<small>◷ Entrada 15:08</small><div class="timer">00:16:59</div></div></div></aside>
</main>
<footer>© 2026 SaltLab Café · Demo de interfaz · Personaliza este proyecto con tu marca</footer>
<div class="notice" id="notice"></div>
<script>
const products=[
['Bebidas','🥃','Highway Vodka Mix',8],['Bebidas','🍋','Lemon Fresh',6],['Bebidas','🥤','Refresco de cola',6],['Bebidas','🍺','Roadhouse Lager',7],['Bebidas','☕','Salt Café',5],['Bebidas','🥛','Vainilla Choco Shake',6],
['Comida','🥨','Aritos Crujientes',6],['Comida','🍔','Bocata Parrillero',6],['Comida','🍟','Gajos Fundidos',6],['Comida','🍖','Parrillada del Camino',6],
['Packs','🧺','Pack 10x10',116],['Packs','🧺','Pack 15x15',174],['Packs','🧺','Pack 3x3',34],['Packs','🧺','Pack 5x5',58],
['Peluche','🧸','Peluche Flammy',25],['Postres','🍮','Choco Crunch',6],['Postres','🍰','Tiramisú Tentación',5]
];
const cats=['Todas','Bebidas','Comida','Packs','Peluche','Postres'];let category='Todas',cart=[];
const money=n=>n.toLocaleString('es-ES',{minimumFractionDigits:2,maximumFractionDigits:2})+' $';
const catalog=document.querySelector('#catalog'),filters=document.querySelector('#filters'),search=document.querySelector('#search');
function renderFilters(){filters.innerHTML=cats.map(c=>`<button class="pill ${c===category?'active':''}" data-cat="${c}">${({Todas:'⭐',Bebidas:'🥤',Comida:'🍔',Packs:'🧺',Peluche:'🧸',Postres:'🍰'})[c]} ${c}</button>`).join('');filters.querySelectorAll('button').forEach(b=>b.onclick=()=>{category=b.dataset.cat;renderFilters();renderCatalog()})}
function renderCatalog(){let q=search.value.toLocaleLowerCase();let list=products.filter(p=>(category==='Todas'||p[0]===category)&&p[2].toLocaleLowerCase().includes(q));catalog.innerHTML=cats.slice(1).map(c=>{let items=list.filter(p=>p[0]===c);if(!items.length)return '';return `<div class="group"><h3 class="group-title">${({Bebidas:'🥤',Comida:'🍔',Packs:'🧺',Peluche:'🧸',Postres:'🍰'})[c]} ${c.toUpperCase()}</h3><div class="products">${items.map(p=>`<button class="product" data-name="${p[2]}"><span class="emoji">${p[1]}</span><span><strong>${p[2]}</strong><span class="price">${money(p[3])}</span></span></button>`).join('')}</div></div>`}).join('')||'<p>No se encontraron productos.</p>';catalog.querySelectorAll('.product').forEach(b=>b.onclick=()=>add(b.dataset.name))}
function add(name){let p=products.find(x=>x[2]===name),item=cart.find(x=>x[2]===name);if(item)item[4]++;else cart.push([...p,1]);renderCart()}
function renderCart(){let el=document.querySelector('#ticketItems');if(!cart.length)el.innerHTML='<div class="empty"><span>🧺</span>Añade productos para empezar.</div>';else el.innerHTML=cart.map(p=>`<div class="ticket-row"><span>${p[1]} ${p[2]} <small>×${p[4]}</small></span><span>${money(p[3]*p[4])} <button data-remove="${p[2]}" aria-label="Quitar uno">−</button></span></div>`).join('');el.querySelectorAll('[data-remove]').forEach(b=>b.onclick=()=>{let p=cart.find(x=>x[2]===b.dataset.remove);p[4]--;if(p[4]<=0)cart=cart.filter(x=>x!==p);renderCart()});let sub=cart.reduce((s,p)=>s+p[3]*p[4],0),rate=Number(document.querySelector('#agreement').value),disc=sub*rate/100;document.querySelector('#subtotal').textContent=money(sub);document.querySelector('#discount').textContent='−'+money(disc);document.querySelector('#total').textContent=money(sub-disc);let btn=document.querySelector('#charge');btn.disabled=!cart.length;btn.classList.toggle('ready',!!cart.length)}
function notice(msg){let n=document.querySelector('#notice');n.textContent=msg;n.style.display='block';setTimeout(()=>n.style.display='none',2600)}
search.addEventListener('input',renderCatalog);document.querySelector('#agreement').addEventListener('change',renderCart);document.querySelector('#charge').onclick=()=>{if(!cart.length)return;notice('¡Cobro registrado! Total: '+document.querySelector('#total').textContent);cart=[];renderCart()};
document.querySelectorAll('.navbtn').forEach(b=>b.onclick=()=>{document.querySelectorAll('.navbtn').forEach(x=>x.classList.toggle('active',x===b));if(b.dataset.page!=='Calculadora')notice('Sección '+b.dataset.page+': demo visual. Añade aquí tus funciones.');});
renderFilters();renderCatalog();renderCart();
</script>
</body></html>
