<!DOCTYPE html><html lang="sv"><head><meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover"><title>Kampspelet</title>
<style>
:root{box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px);color-scheme:dark}
html,body{margin:0;background:#12141c;color:#f2f2f5;font-family:system-ui,sans-serif}
#w{max-width:900px;margin:0 auto;padding:8px}
canvas{width:100%;display:none;border-radius:12px;background:#222}
#mn{text-align:center}
h1{margin:6px 0}
.row{display:flex;gap:6px;justify-content:center;align-items:center;flex-wrap:wrap;margin:6px 0}
.pl{display:grid;grid-template-columns:repeat(auto-fit,minmax(270px,1fr));gap:8px}
.tiles{display:grid;grid-template-columns:1fr 1fr 1fr;gap:5px;margin:8px 0}
.card{background:#1d2030;border-radius:12px;padding:10px;margin:6px 0}
small{color:#aab;display:block;margin:4px 0}
button{background:#2a2f45;color:#fff;border:2px solid transparent;border-radius:8px;padding:8px 10px;font-size:14px;cursor:pointer;touch-action:none;user-select:none}
button.on{border-color:var(--c,#7aa2ff);background:#394063}
input{background:#2a2f45;color:#fff;border:1px solid #556;border-radius:6px;padding:6px}
input[type=color]{padding:0;height:34px;width:44px}
.big{background:#e5533d;font-size:20px;font-weight:bold;padding:12px 40px;margin:8px}
#tc{display:none;justify-content:space-between;flex-wrap:wrap;gap:6px;margin-top:6px}
#tc button{min-width:44px;font-size:17px;padding:12px 10px}
.sp{background:#5a3b8a;font-weight:bold;font-size:20px!important;padding:14px 16px!important}
.sp.rdy{background:#ffd93b;color:#222;box-shadow:0 0 14px #ffd93b}
.lg{display:grid;grid-template-columns:1fr 1fr;gap:5px;text-align:left;font-size:13px;margin-top:8px}
kbd{background:#394063;border-radius:4px;padding:1px 7px;font-weight:bold;font-family:inherit}
</style></head><body><div id="w"><div id="mn"></div><canvas id="cv" width="800" height="450"></canvas><div id="tc"></div></div>
<script>
const CH=[{n:'Eld',e:'🔥',c:'#e5533d',spd:230,dmg:9,hp:100,s:'Eld',d:'Balanserad. Super: eldklot'},
{n:'Is',e:'❄️',c:'#4aa3e0',spd:220,dmg:8,hp:100,s:'Is',d:'Super: frysklot som fryser fienden'},
{n:'Blixt',e:'⚡',c:'#f2c230',spd:290,dmg:7,hp:90,s:'Blixt',d:'Snabb. Super: rusch genom fienden'},
{n:'Tank',e:'🛡️',c:'#4caf6a',spd:170,dmg:12,hp:130,s:'Tank',d:'Seg och tålig. Super: jordskalv'}];
const SUPS=['Eld','Is','Blixt','Tank'],SUPN={Eld:'🔥 Eldklot',Is:'❄️ Frys',Blixt:'⚡ Rusch',Tank:'🛡️ Skalv'};
const SCH=[{n:'WASD',k:{l:'KeyA',r:'KeyD',j:'KeyW',a:'KeyF',s:'KeyG',f:'KeyH'}},{n:'Pilar',k:{l:'ArrowLeft',r:'ArrowRight',j:'ArrowUp',a:'KeyN',s:'KeyM',f:'KeyB'}},{n:'IJKL',k:{l:'KeyJ',r:'KeyL',j:'KeyI',a:'KeyU',s:'KeyO',f:'KeyP'}}];
const $=s=>document.querySelector(s),cv=$('#cv'),mn=$('#mn'),tc=$('#tc'),GY=390;let g=cv.getContext('2d'),PVQ={};
let cfg={mode:'1v1',fmt:'1v1',err:'',sl:[{t:'h',c:0,k:0},{t:'b',c:3,k:1},{t:'b',c:1,k:2},{t:'b',c:2,k:0}],cu:{n:'Min',c:'#ff66cc',sp:3,dm:3,hp:4,s:'Eld'}};
try{Object.assign(cfg.cu,JSON.parse(localStorage.getItem('kampcu')||'{}'))}catch(e){}
cfg.nick='Spelare'+(Math.random()*90+10|0);try{cfg.nick=localStorage.getItem('kampnick')||cfg.nick}catch(e){}
let scr='menu',F=[],FS=[],P=[],FX=[],W=[0,0],rd=1,st=0,ro=0,msg='',DT=0,T=0,keys={},tk=[],AR,HP=null,hpT=6,ROOM=null,nr=null,host=0,net=0,code='',myI=-1,sn=0,lastM=-1;
const gc=n=>{if(n!=4)return CH[n];const u=cfg.cu;return{n:u.n,e:'⭐',c:u.c,spd:150+u.sp*25,dmg:5+u.dm*1.6,hp:70+u.hp*12,s:u.s,d:'Din egen gubbe · Super: '+SUPN[u.s]}};
const cl=(v,a,b)=>Math.max(a,Math.min(b,+v||a));
const sc=c=>({n:String(c.n||'?').replace(/[<>&"]/g,'').slice(0,10),e:String(c.e||'⭐').slice(0,2),c:/^#[0-9a-f]{6}$/i.test(c.c)?c.c:'#ffffff',spd:cl(c.spd,150,300),dmg:cl(c.dmg,5,16),hp:cl(c.hp,70,140),s:SUPS.includes(c.s)?c.s:'Eld'});
const kl=c=>({ArrowLeft:'←',ArrowRight:'→',ArrowUp:'↑'})[c]||c.slice(3);
const leg=n=>{const k=SCH[n].k;return '<div class="lg">'+[['l','Gå vänster'],['r','Gå höger'],['j','Hoppa'],['a','👊 Slag'],['f','🔫 Skjut'],['s','⚡ Super (full stapel)']].map(([b,t])=>'<span><kbd>'+kl(k[b])+'</kbd> '+t+'</span>').join('')+'</div>'};
const act=()=>cfg.mode=='1v1'?[0,2]:[0,1,2,3];
const MODES=[['1v1','1 mot 1'],['2v2','2 mot 2'],['on','🌐 Online']];
function slotCard(i,title,typ){const s=cfg.sl[i];
 let h='<div class="card"><b>'+title+'</b>';
 if(typ)h+='<div class="row"><button data-t="'+i+'">'+(s.t=='h'?'🧑 Människa':'🤖 Bot')+' (byt)</button></div>';
 h+='<div class="tiles">'+[0,1,2,3,4].map(n=>{const c=gc(n);return '<button data-c="'+i+','+n+'" class="'+(s.c==n?'on':'')+'" style="--c:'+c.c+'">'+c.e+' '+c.n+'</button>'}).join('')+'</div><small>'+gc(s.c).d+'</small>';
 if(s.t=='h')h+='<div class="row">'+SCH.map((x,n)=>'<button data-k="'+i+','+n+'" class="'+(s.k==n?'on':'')+'">'+x.n+'</button>').join('')+'</div>'+leg(s.k);
 return h+'</div>'}
function builder(){const u=cfg.cu,left=10-u.sp-u.dm-u.hp;
 return '<div class="card"><b>🛠️ Bygg din egen gubbe</b><small>Välj den som ⭐ i listan ovan.</small><canvas id="pv" width="170" height="160" style="display:block;width:170px;margin:6px auto;background:#12141c;border-radius:10px"></canvas><div class="row"><input id="bn" value="'+u.n+'" maxlength="10" style="width:110px"><input id="bc" type="color" value="'+u.c+'"></div>'+[['sp','Fart'],['dm','Styrka'],['hp','Hälsa']].map(([k,t])=>'<div class="row">'+t+' <input type="range" min="1" max="5" value="'+u[k]+'" data-s="'+k+'"> '+u[k]+'</div>').join('')+'<small>Poäng kvar: '+left+' (max 10 totalt)</small><div class="row">Super: '+SUPS.map(s=>'<button data-u="'+s+'" class="'+(u.s==s?'on':'')+'">'+SUPN[s]+'</button>').join('')+'</div></div>'}
const nk=p=>String(p.presence.nk||'Spelare').replace(/[<>&"]/g,'').slice(0,12)+(p.presence.h?' 👑':'');
const card=(k,p,extra)=>{const ch=p.presence.ch?sc(p.presence.ch):null;if(ch)PVQ[k]=ch;return '<div style="display:inline-block;text-align:center;margin:4px;padding:6px;background:#12141c;border-radius:10px;min-width:96px">'+(ch?'<canvas class="pv" data-i="'+k+'" width="100" height="135" style="width:70px;display:block;margin:auto"></canvas>':'')+'<b>'+nk(p)+'</b>'+(p.isMe?' (du)':'')+'<small>'+extra+'</small></div>'};
const ppl=()=>nr?nr.peers().filter(p=>p.kind=='viewer').map((p,i)=>card('r'+i,p,(p.presence.ch&&sc(p.presence.ch).n)||'')).join(''):'';
const onl=()=>ROOM?ROOM.peers().filter(p=>p.kind=='viewer').map((p,i)=>card('o'+i,p,p.presence.rc?'rum '+String(p.presence.rc).replace(/[<>&"]/g,'').slice(0,12):'i lobbyn')).join(''):'';
function lobby(){
 if(!ROOM)return '<div class="card">Online fungerar när sidan är öppen på claude.ai och du är inloggad. Din kompis måste också vara inloggad och ha fått sidan delad med sig.</div>';
 if(!nr)return '<div class="card"><b>Ditt namn</b> <input id="nk" value="'+cfg.nick+'" maxlength="12" style="width:110px"></div><div class="card"><b>👥 Online nu</b><div id="on">'+onl()+'</div></div><div class="card"><b>Rumskod</b><div class="row"><input id="rc" value="'+code+'" maxlength="12" style="width:110px"><button data-cr="1">Skapa rum (värd)</button><button data-jn="1">Gå med</button></div><small>Båda skriver samma kod. Värden skapar, kompisen går med.</small><small style="color:#f88">'+cfg.err+'</small></div>'+slotCard(0,'Din gubbe',0);
 return '<div class="card"><b>Rum '+code+(host?' · du är värd 👑':'')+'</b><div id="pp">'+ppl()+'</div>'+(host?'<div class="row"><button data-f="1v1" class="'+(cfg.fmt=='1v1'?'on':'')+'">1 mot 1</button><button data-f="2v2" class="'+(cfg.fmt=='2v2'?'on':'')+'">2 mot 2 (bottar fyller)</button></div><small>3–4 spelare ger automatiskt 2 mot 2.</small>':'<small>Väntar på att värden startar…</small>')+'<small style="color:#f88">'+cfg.err+'</small></div>'+slotCard(0,'Din gubbe',0)}
function menu(){PVQ={};
 let h='<h1>⚔️ Kampspelet</h1><div class="row">'+MODES.map(([m,t])=>'<button data-m="'+m+'" class="'+(cfg.mode==m?'on':'')+'">'+t+'</button>').join('')+'</div>';
 if(cfg.mode=='on')h+=lobby();
 else{const a=cfg.mode=='1v1'?[[0],[2]]:[[0,1],[2,3]];
  h+='<div class="pl">'+a.map((t,ti)=>'<div>'+t.map((i,j)=>slotCard(i,(ti?'Höger lag':'Vänster lag')+(cfg.mode=='2v2'?' · '+(j+1):''),1)).join('')+'</div>').join('')+'</div><div class="row"><button data-sw="1">⇄ Byt sida</button></div>'}
 h+=builder()+'<small>Under spelplanen finns även knappar (🔫 Skjut, ⚡ Super) du kan klicka eller trycka på. Banan byts varje runda.</small>';
 if(cfg.mode!='on'||(nr&&host))h+='<button class="big" data-go="1">▶ Starta (Enter)</button>';
 mn.innerHTML=h;mn.style.display='block';cv.style.display='none';tc.style.display='none';scr='menu';
 if(ROOM)ROOM.presence({ch:gc(cfg.sl[0].c),nk:cfg.nick}).catch(()=>{});if(nr)nr.presence({ch:gc(cfg.sl[0].c),nk:cfg.nick}).catch(()=>{})}
function fixK(p){const used=[cfg.sl[p].k];act().forEach(i=>{const s=cfg.sl[i];if(i==p||s.t!='h')return;if(used.includes(s.k))s.k=[0,1,2].find(n=>!used.includes(n));used.push(s.k)})}
const sv=()=>{try{localStorage.setItem('kampcu',JSON.stringify(cfg.cu));localStorage.setItem('kampnick',cfg.nick)}catch(e){}};
mn.onclick=e=>{const b=e.target.closest('button');if(!b)return;const d=b.dataset;
 if(d.m){cfg.mode=d.m;fixK(0)}
 if(d.t){const s=cfg.sl[d.t];if(s.t=='b'){if(act().filter(i=>cfg.sl[i].t=='h').length>=3)return;s.t='h';fixK(+d.t)}else s.t='b'}
 if(d.c){const[i,n]=d.c.split(',').map(Number);cfg.sl[i].c=n}
 if(d.k){const[i,n]=d.k.split(',').map(Number);cfg.sl[i].k=n;fixK(i)}
 if(d.sw){[[0,2],[1,3]].forEach(([a,b])=>{[cfg.sl[a],cfg.sl[b]]=[cfg.sl[b],cfg.sl[a]]})}
 if(d.u){cfg.cu.s=d.u;sv()}
 if(d.f)cfg.fmt=d.f;
 if(d.cr||d.jn){code=($('#rc').value||'').toLowerCase().replace(/[^a-z0-9]/g,'')||'x'+Math.random().toString(36).slice(2,6);host=d.cr?1:0;return joinRoom()}
 if(d.go)return cfg.mode=='on'?hostStart():start();
 menu()};
mn.onchange=e=>{const t=e.target,u=cfg.cu;
 if(t.id=='nk')cfg.nick=t.value.replace(/[<>&"]/g,'').slice(0,12)||'Spelare';
 if(t.id=='bn')u.n=t.value.replace(/[<>&"]/g,'').slice(0,10)||'Min';
 if(t.id=='bc')u.c=t.value;
 if(t.dataset.s){const k=t.dataset.s,o=u[k];u[k]=+t.value;if(u.sp+u.dm+u.hp>10)u[k]=o}
 sv();menu()};
async function joinRoom(){try{nr=await ROOM.join('kamp-'+code);
  nr.onPeers(()=>{const p=$('#pp');if(p)p.innerHTML=ppl()});
  nr.on('go',m=>{if(!m.isMe&&!host)beginOnline(m.data)});
  nr.on('st',m=>{if(!m.isMe&&!host)onSt(m.data)});
  nr.on('fx',m=>{if(!m.isMe&&!host)FX.push({x:+m.data.x||0,t:.5,col:'#4caf6a'})});
  nr.on('over',m=>{if(!m.isMe&&!host)endScr(+m.data.w)});
  ROOM.presence({rc:code}).catch(()=>{});await nr.presence({t:Date.now(),h:host,ch:gc(cfg.sl[0].c),nk:cfg.nick,in:0});cfg.err=''}catch(e){nr=null;cfg.err='Kunde inte gå med i rummet.'}menu()}
const meP=()=>{const p=nr&&nr.peers().find(p=>p.isMe&&p.sameTab);return p&&p.peer};
function hostStart(){const hs=nr.peers().filter(p=>p.kind=='viewer'&&p.presence.t).sort((a,b)=>a.presence.t-b.presence.t).slice(0,4),n=hs.length,two=cfg.fmt=='2v2'||n>2;
 const pl=hs.map((p,i)=>({pe:p.peer,ch:p.presence.ch||CH[0],team:i%2}));
 if(two)[0,1].forEach(t=>{while(pl.filter(x=>x.team==t).length<2)pl.push({pe:null,ch:CH[(pl.length+1)%4],team:t})});
 else if(n<2)pl.push({pe:null,ch:CH[1],team:1});
 const go={pl};nr.emit('go',go).then(()=>beginOnline(go),()=>{cfg.err='Du saknar behörighet att starta här.';menu()})}
function beginOnline(d){net=1;const me=meP();FS=d.pl.slice(0,4).map(p=>({team:p.team?1:0,ch:sc(p.ch),hum:!!p.pe,pe:p.pe,loc:!!p.pe&&p.pe==me,kk:cfg.sl[0].k}));go()}
function start(){net=0;FS=act().map(i=>{const s=cfg.sl[i];return{team:i<2?0:1,ch:gc(s.c),hum:s.t=='h',pe:null,loc:s.t=='h',kk:s.k}});go()}
function go(){W=[0,0];rd=1;tk=[{},{},{},{}];lastM=-1;newRound();scr='fight';mn.style.display='none';cv.style.display='block';
 tc.innerHTML=F.map((f,i)=>f.loc?'<div class="row"><b>'+f.c.n+'</b>'+[['l','◀'],['r','▶'],['j','⤒ Hoppa'],['a','👊 Slag'],['f','🔫 SKJUT'],['s','⚡ SUPER']].map(([b,t])=>'<button data-p="'+i+'" data-b="'+b+'"'+(b=='s'?' class="sp"':'')+'>'+t+'</button>').join('')+'</div>':'').join('');
 tc.style.display='flex'}
tc.addEventListener('pointerdown',e=>{const b=e.target.closest('button');if(!b)return;e.preventDefault();b.setPointerCapture(e.pointerId);tk[b.dataset.p][b.dataset.b]=1});
['pointerup','pointercancel'].forEach(n=>tc.addEventListener(n,e=>{const b=e.target.closest('button');if(b)tk[b.dataset.p][b.dataset.b]=0}));
function mkAll(){const cnt=[0,0];F=FS.map((s,i)=>{const j=cnt[s.team]++,c=s.ch;return{i,team:s.team,hum:s.hum,pe:s.pe,loc:s.loc,kk:s.kk,c,x:s.team?680-j*70:120+j*70,y:GY,vx:0,vy:0,kb:0,f:s.team?-1:1,hp:c.hp,mx:c.hp,m:0,cd:0,sw:0,fz:0,dash:0,dh:0,hit:0,pa:0,ps:0,wk:0,sc:0,sh:0,gr:1,ai:{t:0,in:{}},tx:0,ty:0}})}
const ARN=[{n:'Skogen',a:'#1f3b2d',b:'#3d6b4a',gc:'#2d4a2f',d:'trees',pl:[{x:120,w:150,y:290},{x:530,w:150,y:290}]},
{n:'Vulkanen',a:'#2a0f12',b:'#7a2a1a',gc:'#3a1a16',d:'volc',pl:[{x:330,w:140,y:285},{x:80,w:110,y:310},{x:610,w:110,y:310}]},
{n:'Isgrottan',a:'#12304a',b:'#5aa0c8',gc:'#cfe8f5',d:'ice',pl:[{x:100,w:130,y:300},{x:570,w:130,y:300},{x:335,w:130,y:230}]},
{n:'Stadsnatt',a:'#0c0c24',b:'#3a1f5a',gc:'#1a1a2e',d:'city',pl:[{x:250,w:300,y:300}]}];
function newRound(){AR=ARN[(rd-1)%4];HP=null;hpT=6;mkAll();P=[];FX=[];st=1.1;ro=0;msg='Runda '+rd+' · '+AR.n}
const names=t=>F.filter(f=>f.team==t).map(f=>f.c.n).join(' + ');
function endScr(w){scr='menu';cv.style.display='none';tc.style.display='none';mn.style.display='block';
 mn.innerHTML='<h1>🏆 '+names(w)+' vinner!</h1>'+(net?'':'<button class="big" data-go="1">Spela igen</button>')+'<button class="big" style="background:#394063" onclick="menu()">Meny</button>'}
function finish(){const w=W[0]>=2?0:1;if(net)nr.emit('over',{w}).catch(()=>{});endScr(w)}
const enc=i=>(i.l?1:0)|(i.r?2:0)|(i.j?4:0)|(i.a?8:0)|(i.f?16:0)|(i.s?32:0),dec=m=>({l:m&1,r:m&2,j:m&4,a:m&8,f:m&16,s:m&32});
function lin(f){const k=SCH[f.kk].k,t=tk[f.i]||{};return{l:keys[k.l]||t.l,r:keys[k.r]||t.r,j:keys[k.j]||t.j,a:keys[k.a]||t.a,s:keys[k.s]||t.s,f:keys[k.f]||t.f}}
function inp(f){if(f.loc)return lin(f);if(f.pe){const p=nr&&nr.peers().find(p=>p.peer==f.pe);return dec(p&&+p.presence.in||0)}return ai(f)}
const foe=f=>F.filter(e=>e.team!=f.team&&e.hp>0).sort((a,b)=>Math.abs(a.x-f.x)-Math.abs(b.x-f.x))[0];
function ai(f){const o=foe(f),a=f.ai;if(!o)return{};a.t-=DT;
 if(a.t<=0){a.t=.12+Math.random()*.12;const d=o.x-f.x,ad=Math.abs(d),i={l:0,r:0,j:0,a:0,s:0,f:0};
  if(ad>75){d>0?i.r=1:i.l=1}else if(Math.random()<.25){d>0?i.l=1:i.r=1}
  if(ad<85&&Math.random()<.55)i.a=1;
  if(ad>160&&Math.random()<.3)i.f=1;
  if(Math.random()<.05)i.j=1;
  if(f.m>=100&&ad<320&&Math.random()<.5)i.s=1;
  a.in=i}
 const r=a.in;a.in={...r,a:0,s:0,j:0,f:0};return r}
function dmg(t,s,d,kb){t.hp-=d;t.kb=s.f*kb;t.hit=.2;s.m=Math.min(100,s.m+d*1.2);t.m=Math.min(100,t.m+d*.8)}
const en=f=>F.filter(e=>e.team!=f.team&&e.hp>0);
function sup(f){const n=f.c.s;
 if(n=='Eld')P.push({x:f.x+f.f*30,y:f.y-55,v:f.f*520,d:24,col:'#ff7a2a',o:f,r:16});
 if(n=='Is')P.push({x:f.x+f.f*30,y:f.y-55,v:f.f*600,d:10,fz:1,col:'#8fdcff',o:f,r:16});
 if(n=='Blixt'){f.dash=.28;f.dh=0}
 if(n=='Tank'){FX.push({x:f.x,t:.5,col:'#4caf6a'});if(net)nr.emit('fx',{x:f.x}).catch(()=>{});en(f).forEach(e=>{if(e.gr&&Math.abs(e.x-f.x)<240)dmg(e,f,26,600)})}}
function upd(f,dt){const o=foe(f);if(!o)return;const i={...inp(f)},c=f.c;
 f.cd-=dt;f.sw-=dt;f.fz-=dt;f.hit-=dt;f.sc-=dt;f.sh-=dt;
 if(f.fz>0)i.l=i.r=i.j=i.a=i.s=i.f=0;
 if(f.dash>0){f.dash-=dt;f.vx=900*f.f;const e=en(f).find(e=>Math.abs(e.x-f.x)<45&&Math.abs(e.y-f.y)<80);if(!f.dh&&e){f.dh=1;dmg(e,f,28,500)}}
 else{f.vx=((i.r?1:0)-(i.l?1:0))*c.spd;f.f=o.x>f.x?1:-1}
 f.kb*=Math.pow(.01,dt);
 f.x=Math.max(30,Math.min(770,f.x+(f.vx+f.kb)*dt));
 if(f.vx)f.wk+=dt*14;
 if(i.j&&f.gr)f.vy=-700;
 const py=f.y;f.vy+=1800*dt;f.y+=f.vy*dt;f.gr=0;
 if(f.y>=GY){f.y=GY;f.vy=0;f.gr=1}
 else if(f.vy>=0)for(const pl of AR.pl)if(f.x>pl.x-10&&f.x<pl.x+pl.w+10&&py<=pl.y&&f.y>=pl.y){f.y=pl.y;f.vy=0;f.gr=1}
 if(i.a&&!f.pa&&f.cd<=0){f.sw=.18;f.cd=.38;
  en(f).forEach(e=>{if(Math.abs(e.x-f.x)<90&&Math.abs(e.y-f.y)<70&&(e.x-f.x)*f.f>-20)dmg(e,f,c.dmg,320)})}
 f.pa=i.a;
 if(i.f&&f.sc<=0){f.sc=.5;f.sh=.15;P.push({x:f.x+f.f*50,y:f.y-66,v:f.f*750,d:4,col:c.c,o:f,r:5,kb:100})}
 if(i.s&&!f.ps&&f.m>=100){f.m=0;sup(f)}
 f.ps=i.s}
function snap(dt){if(!net||!host)return;sn-=dt;if(sn>0)return;sn=.05;const q=n=>Math.round(n*100)/100;
 nr.emit('st',{a:ARN.indexOf(AR),s:q(st),o:q(ro),m:msg,w:W,r:rd,h:HP?[HP.x|0,HP.y|0]:0,f:F.map(f=>[f.x|0,f.y|0,q(f.hp),q(f.m),f.f,q(f.sw),q(f.sh),q(f.fz),q(f.hit)]),p:P.map(p=>[p.x|0,p.y|0,p.v|0,p.r,p.col])}).catch(()=>{})}
function onSt(d){if(!F.length||scr!='fight')return;AR=ARN[d.a]||AR;HP=d.h?{x:d.h[0],y:d.h[1]}:null;st=d.s;ro=d.o;msg=d.m;W=d.w;rd=d.r;
 d.f.forEach((a,i)=>{const f=F[i];if(!f)return;[f.tx,f.ty,f.hp,f.m,f.f,f.sw,f.sh,f.fz,f.hit]=a;if(!f.init){f.x=f.tx;f.y=f.ty;f.init=1}});
 P=d.p.map(a=>({x:a[0],y:a[1],v:a[2],r:a[3],col:a[4]}))}
function step(dt){DT=dt;T+=dt;FX=FX.filter(e=>(e.t-=dt)>0);
 if(net&&!host){F.forEach(f=>{if(f.init){if(Math.abs(f.tx-f.x)>1)f.wk+=dt*14;f.x+=(f.tx-f.x)*.5;f.y+=(f.ty-f.y)*.5}});P.forEach(p=>p.x+=p.v*dt);
  const me=F[myI=F.findIndex(f=>f.loc)];if(me){const m=enc(lin(me));if(m!=lastM){lastM=m;nr.presence({in:m}).catch(()=>{})}}return}
 if(st>0){st-=dt;snap(dt);return}
 if(!ro){F.forEach(f=>f.hp>0&&upd(f,dt));
  if(!HP){hpT-=dt;if(hpT<=0){const pl=AR.pl[Math.floor(Math.random()*AR.pl.length)];HP={x:pl.x+pl.w/2,y:pl.y-30}}}
  else F.forEach(f=>{if(HP&&f.hp>0&&Math.abs(f.x-HP.x)<30&&Math.abs(f.y-40-HP.y)<50){f.hp=Math.min(f.mx,f.hp+20);HP=null;hpT=9}});
  P=P.filter(p=>{p.x+=p.v*dt;const t=en(p.o).find(t=>Math.abs(p.x-t.x)<30&&Math.abs(p.y-(t.y-50))<55);
   if(t){dmg(t,p.o,p.d,p.kb||450);if(p.fz)t.fz=1.5;return 0}return p.x>-40&&p.x<840});
  const al=[0,1].map(k=>F.some(f=>f.team==k&&f.hp>0));
  if(!al[0]||!al[1]){ro=1.8;const w=al[0]?0:1;W[w]++;rd++;msg='KO! '+names(w)+' tar rundan'}}
 else{ro-=dt;if(ro<=0){if(W[0]>=2||W[1]>=2)finish();else newRound()}}
 snap(dt)}
function dF(f){const c=f.c,w=c.s=='Tank'?44:32,X=f.x,Y=f.y,q=f.f;
 const arm=(hx,hy,r)=>{g.strokeStyle=c.c;g.lineWidth=7;g.beginPath();g.moveTo(X,Y-70);g.lineTo(hx,hy);g.stroke();g.fillStyle='#f3d3b0';g.beginPath();g.arc(hx,hy,r,0,7);g.fill()};
 if(f.hp<=0)g.globalAlpha=.25;
 g.fillStyle='rgba(0,0,0,.3)';g.beginPath();g.ellipse(X,Y+2,24,6,0,0,7);g.fill();
 g.strokeStyle=c.c;g.lineWidth=8;g.lineCap='round';
 const s=Math.sin(f.wk)*10;
 g.beginPath();g.moveTo(X-8,Y-35);g.lineTo(X-8+s,Y);g.moveTo(X+8,Y-35);g.lineTo(X+8-s,Y);g.stroke();
 arm(X-q*16,Y-48,6);
 g.fillStyle=c.c;g.fillRect(X-w/2,Y-80,w,48);
 g.fillStyle='#f3d3b0';g.beginPath();g.arc(X,Y-95,15,0,7);g.fill();
 g.fillStyle='#111';g.fillRect(X+q*6-2,Y-98,4,4);
 if(c.s=='Eld'){g.fillStyle='#ff9a3a';g.beginPath();g.moveTo(X-12,Y-106);g.lineTo(X-6,Y-126);g.lineTo(X,Y-108);g.lineTo(X+6,Y-128);g.lineTo(X+12,Y-106);g.fill()}
 if(c.s=='Blixt'){g.fillStyle=c.c;g.fillRect(X-15,Y-104,30,5)}
 if(c.s=='Is'){g.fillStyle='#bfe6ff';g.beginPath();g.moveTo(X-10,Y-106);g.lineTo(X,Y-124);g.lineTo(X+10,Y-106);g.fill()}
 if(f.sw>0)arm(X+q*66,Y-66,10);
 else if(f.sh>0){arm(X+q*44,Y-68,6);g.fillStyle='#333';g.fillRect(q>0?X+q*44:X+q*44-14,Y-72,14,6);g.fillStyle='#ffe066';g.beginPath();g.arc(X+q*62,Y-69,6,0,7);g.fill()}
 else arm(X+q*26,Y-52+Math.sin(T*6)*2,6);
 if(f.fz>0){g.fillStyle='rgba(140,220,255,.55)';g.fillRect(X-30,Y-122,60,124)}
 if(f.hit>0){g.fillStyle='rgba(255,255,255,.5)';g.fillRect(X-w/2,Y-80,w,48)}
 g.globalAlpha=1}
function hud(){[0,1].forEach(t=>F.filter(f=>f.team==t).forEach((f,j)=>{const bw=300,X=t?480:20,y=10+j*40;
 g.fillStyle='#0008';g.fillRect(X,y,bw,16);
 const r=Math.max(0,f.hp/f.mx)*bw;g.fillStyle=f.c.c;g.fillRect(t?X+bw-r:X,y,r,16);
 g.fillStyle='#0008';g.fillRect(X,y+18,bw,7);
 g.fillStyle=f.m>=100?'#ffd93b':'#b36bff';g.fillRect(t?X+bw-f.m/100*bw:X,y+18,f.m/100*bw,7);
 g.fillStyle='#fff';g.font='bold 12px system-ui';g.textAlign=t?'right':'left';
 g.fillText(f.c.n+(f.hum?'':' 🤖')+(f.m>=100?'  ⚡ SUPER REDO':''),t?X+bw-4:X+4,y+12)}));
 g.font='bold 22px system-ui';g.textAlign='center';g.fillStyle='#fff';g.fillText(W[0]+' : '+W[1],400,30);
 g.font='11px system-ui';g.fillStyle='#ccd';
 [0,1].forEach(t=>F.filter(f=>f.loc&&f.team==t).forEach((f,j)=>{const k=SCH[f.kk].k;g.textAlign=t?'right':'left';
  g.fillText(f.c.n+': '+['l','r','j','a','f','s'].map((b,n)=>kl(k[b])+'='+['←','→','hoppa','slag','skjut','super'][n]).join(' '),t?780:20,440-j*13)}))}
function bg(){const gr=g.createLinearGradient(0,0,0,450);gr.addColorStop(0,AR.a);gr.addColorStop(1,AR.b);g.fillStyle=gr;g.fillRect(0,0,800,450);
 const d=AR.d;
 if(d=='trees'){for(let i=0;i<6;i++){const x=60+i*140;g.fillStyle='#3b2a1a';g.fillRect(x-6,GY-90,12,90);g.fillStyle='#2f7a44';g.beginPath();g.moveTo(x-40,GY-80);g.lineTo(x,GY-200);g.lineTo(x+40,GY-80);g.fill()}}
 if(d=='volc'){g.fillStyle='#1c0a0c';g.beginPath();g.moveTo(150,GY);g.lineTo(400,120);g.lineTo(650,GY);g.fill();g.fillStyle='#ff6a1a';g.globalAlpha=.7;for(let i=0;i<12;i++){g.beginPath();g.arc(300+i*18+Math.sin(T+i)*20,GY-((T*40+i*37)%260),3,0,7);g.fill()}g.globalAlpha=1}
 if(d=='ice'){g.fillStyle='#bfe6ff';for(let i=0;i<12;i++){g.beginPath();g.moveTo(i*70,0);g.lineTo(i*70+35,60+(i%3)*25);g.lineTo(i*70+70,0);g.fill()}g.fillStyle='#fff';for(let i=0;i<30;i++)g.fillRect((i*97+T*15)%800,(i*53+T*40)%GY,3,3)}
 if(d=='city'){g.fillStyle='#fff';g.beginPath();g.arc(650,90,28,0,7);g.fill();for(let i=0;i<9;i++){const h=120+(i*53)%110,x=i*90;g.fillStyle='#15152e';g.fillRect(x,GY-h,76,h);g.fillStyle='#ffd966';for(let j=0;j<h/30-1;j++)if((i+j)%3){g.fillRect(x+12,GY-h+12+j*30,10,14);g.fillRect(x+44,GY-h+12+j*30,10,14)}}}
 g.fillStyle=AR.gc;g.fillRect(0,GY,800,60);
 g.fillStyle=d=='volc'?'#ff5a1a':'#ffffff33';g.fillRect(0,GY,800,4);
 AR.pl.forEach(p=>{g.fillStyle='#00000044';g.fillRect(p.x,p.y+10,p.w,6);g.fillStyle=d=='ice'?'#e8f6ff':'#8b7a66';g.fillRect(p.x,p.y,p.w,10)})}
function draw(){bg();
 FX.forEach(e=>{g.strokeStyle=e.col;g.lineWidth=6;g.globalAlpha=Math.min(1,e.t*2);g.beginPath();g.ellipse(e.x,GY,(.5-e.t)*480,14,0,0,7);g.stroke();g.globalAlpha=1});
 if(HP){g.font='26px system-ui';g.textAlign='center';g.fillStyle='#fff';g.fillText('❤️',HP.x,HP.y+Math.sin(T*4)*5)}
 F.forEach(dF);
 P.forEach(p=>{g.fillStyle=p.col;g.beginPath();g.arc(p.x,p.y,p.r,0,7);g.fill();if(p.r<8){g.fillStyle='#fff';g.beginPath();g.arc(p.x,p.y,2,0,7);g.fill()}});
 hud();
 document.querySelectorAll('.sp').forEach(b=>{const f=F[+b.dataset.p];b.classList.toggle('rdy',!!f&&f.m>=100)});
 if(st>0||ro>0){g.fillStyle='#fff';g.font='bold 34px system-ui';g.textAlign='center';g.fillText(ro>0?msg:(st>.45?msg:'KÄMPA!'),400,190)}}
let last=0;
function prev(){const c=$('#pv');if(!c)return;const o=g;g=c.getContext('2d');g.clearRect(0,0,170,160);const k=T%3;dF({c:gc(4),x:60,y:140,f:1,hp:1,wk:0,sw:k<.18?1:0,sh:k>1.5&&k<1.65?1:0,fz:0,hit:0});g=o}
function pq(){const o=g;document.querySelectorAll('canvas.pv').forEach(cn=>{const c=PVQ[cn.dataset.i];if(!c)return;const x=cn.getContext('2d');x.clearRect(0,0,100,135);g=x;dF({c,x:50,y:128,f:1,hp:1,sw:0,sh:0,fz:0,hit:0,wk:0})});g=o}
function loop(t){const dt=Math.min(.033,(t-last)/1000||0);last=t;if(scr=='fight'){step(dt);draw()}else{T+=dt;prev();pq()}requestAnimationFrame(loop)}
addEventListener('keydown',e=>{if(scr=='fight'&&e.code.startsWith('Arrow'))e.preventDefault();
 if(scr=='menu'&&e.code=='Enter'&&e.target.tagName!='INPUT'){if(cfg.mode!='on')start();else if(nr&&host)hostStart()}keys[e.code]=1});
addEventListener('keyup',e=>{keys[e.code]=0});
addEventListener('blur',()=>{keys={}});
try{window.claude&&claude.use('room').then(r=>{ROOM=r;r.onPeers(()=>{const o=$('#on');if(o)o.innerHTML=onl()});if(scr=='menu'&&cfg.mode=='on')menu()}).catch(()=>{})}catch(e){}
menu();requestAnimationFrame(loop);
</script></body></html>
