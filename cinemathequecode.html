import { useState, useEffect, useRef, useCallback } from "react";

// ─── GLOBAL CSS ───────────────────────────────────────────────────────────────
const CSS = `
  @import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;1,300;1,400;1,500&family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Jost:wght@200;300;400;500&display=swap');
  *,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
  :root{
    --bg:#1c1812;--bg2:#221e16;--bg3:#2a2520;--bg4:#322d26;--bg5:#3a332a;
    --border:rgba(200,169,110,.13);--border2:rgba(200,169,110,.28);--border3:rgba(200,169,110,.06);
    --gold:#c8a96e;--gold2:#e2c88a;--gdim:rgba(200,169,110,.4);
    --text:#ede8e0;--text2:#b8afa4;--text3:#7a7068;--text4:#4a4540;
    --red:#b85040;--teal:#5e9e96;--teal2:#7ab8b0;
    --serif:'Cormorant Garamond',Georgia,serif;
    --display:'Playfair Display',Georgia,serif;
    --sans:'Jost',system-ui,sans-serif;
  }
  html,body{min-height:100%;background:var(--bg);color:var(--text);font-family:var(--serif)}
  ::-webkit-scrollbar{width:4px}::-webkit-scrollbar-thumb{background:var(--gdim);border-radius:2px}
  input,button,textarea,select{font-family:inherit}
  input::placeholder,textarea::placeholder{color:var(--text3)}
  input:focus,textarea:focus{outline:none;border-color:var(--gdim)!important}
  @keyframes fadeUp{from{opacity:0;transform:translateY(16px)}to{opacity:1;transform:translateY(0)}}
  @keyframes fadeIn{from{opacity:0}to{opacity:1}}
  @keyframes spin{to{transform:rotate(360deg)}}
  @keyframes orb{0%,100%{box-shadow:0 0 28px rgba(200,169,110,.14);transform:scale(1)}50%{box-shadow:0 0 56px rgba(200,169,110,.34);transform:scale(1.07)}}
  @keyframes orbTeal{0%,100%{box-shadow:0 0 28px rgba(94,158,150,.14);transform:scale(1)}50%{box-shadow:0 0 56px rgba(94,158,150,.3);transform:scale(1.07)}}
  @keyframes barFill{from{width:0}}
  @keyframes slideIn{from{transform:translateX(22px);opacity:0}to{transform:translateX(0);opacity:1}}
  @keyframes shimmer{0%{background-position:-400px 0}100%{background-position:400px 0}}
  @keyframes popIn{from{opacity:0;transform:scale(.92)}to{opacity:1;transform:scale(1)}}
  .fadeUp  {animation:fadeUp  .44s cubic-bezier(.22,1,.36,1) both}
  .fadeIn  {animation:fadeIn  .3s ease both}
  .slideIn {animation:slideIn .38s cubic-bezier(.22,1,.36,1) both}
  .popIn   {animation:popIn   .28s cubic-bezier(.22,1,.36,1) both}
  .hcard{transition:transform .22s,box-shadow .22s,border-color .22s}
  .hcard:hover{transform:translateY(-4px);box-shadow:0 16px 48px rgba(0,0,0,.5);border-color:var(--border2)!important}
  .hbtn:hover{opacity:.76}
  .hlink:hover{color:var(--gold2)!important}
  .hspin{animation:spin .72s linear infinite}
  .skeleton{background:linear-gradient(90deg,var(--bg3) 25%,var(--bg4) 50%,var(--bg3) 75%);background-size:400px 100%;animation:shimmer 1.4s infinite}
`;
if(!document.getElementById("cine-css")){const s=document.createElement("style");s.id="cine-css";s.textContent=CSS;document.head.appendChild(s);}

// ─── SVG ICONS ────────────────────────────────────────────────────────────────
const P={
  film:     <><rect x="2" y="3" width="20" height="18" rx="2" strokeWidth="1.3" fill="none"/><line x1="7" y1="3" x2="7" y2="21" strokeWidth="1.1"/><line x1="17" y1="3" x2="17" y2="21" strokeWidth="1.1"/><line x1="2" y1="8" x2="7" y2="8" strokeWidth="1.1"/><line x1="2" y1="16" x2="7" y2="16" strokeWidth="1.1"/><line x1="17" y1="8" x2="22" y2="8" strokeWidth="1.1"/><line x1="17" y1="16" x2="22" y2="16" strokeWidth="1.1"/></>,
  bookmark: <path d="M5 3h14a1 1 0 011 1v16l-7.5-4.5L5 20V4a1 1 0 011-1z" strokeWidth="1.3" fill="none"/>,
  compass:  <><circle cx="12" cy="12" r="9" strokeWidth="1.3" fill="none"/><path d="M16.5 7.5l-3 6-6 3 3-6 6-3z" strokeWidth="1.2" fill="none"/></>,
  dna:      <><path d="M6 3c0 4 6 4 6 8s-6 4-6 8" strokeWidth="1.5" fill="none" strokeLinecap="round"/><path d="M18 3c0 4-6 4-6 8s6 4 6 8" strokeWidth="1.5" fill="none" strokeLinecap="round"/><line x1="7.5" y1="6.5" x2="16.5" y2="6.5" strokeWidth="1.1" strokeLinecap="round"/><line x1="7.5" y1="17.5" x2="16.5" y2="17.5" strokeWidth="1.1" strokeLinecap="round"/></>,
  moon:     <path d="M21 12.79A9 9 0 1111.21 3 7 7 0 0021 12.79z" strokeWidth="1.3" fill="none"/>,
  eye:      <><path d="M1 12s4-8 11-8 11 8 11 8-4 8-11 8-11-8-11-8z" strokeWidth="1.3" fill="none"/><circle cx="12" cy="12" r="3" strokeWidth="1.2" fill="none"/></>,
  star:     <polygon points="12,2 15.09,8.26 22,9.27 17,14.14 18.18,21.02 12,17.77 5.82,21.02 7,14.14 2,9.27 8.91,8.26" strokeWidth="1.3" fill="none"/>,
  starFill: <polygon points="12,2 15.09,8.26 22,9.27 17,14.14 18.18,21.02 12,17.77 5.82,21.02 7,14.14 2,9.27 8.91,8.26" strokeWidth="0" fill="currentColor"/>,
  search:   <><circle cx="11" cy="11" r="7" strokeWidth="1.4" fill="none"/><line x1="16.5" y1="16.5" x2="21" y2="21" strokeWidth="1.5" strokeLinecap="round"/></>,
  plus:     <><line x1="12" y1="5" x2="12" y2="19" strokeWidth="1.5" strokeLinecap="round"/><line x1="5" y1="12" x2="19" y2="12" strokeWidth="1.5" strokeLinecap="round"/></>,
  x:        <><line x1="18" y1="6" x2="6" y2="18" strokeWidth="1.5" strokeLinecap="round"/><line x1="6" y1="6" x2="18" y2="18" strokeWidth="1.5" strokeLinecap="round"/></>,
  refresh:  <><polyline points="1 4 1 10 7 10" strokeWidth="1.4" fill="none" strokeLinecap="round" strokeLinejoin="round"/><path d="M3.51 15a9 9 0 102.13-9.36L1 10" strokeWidth="1.4" fill="none" strokeLinecap="round"/></>,
  sparkle:  <><path d="M12 2l1.8 5.4L19 9l-5.2 1.8L12 16l-1.8-5.2L5 9l5.2-1.6L12 2z" strokeWidth="1.2" fill="none"/><path d="M19 15l.8 2.4L22 18l-2.2.8L19 21l-.8-2.2L16 18l2.2-.8L19 15z" strokeWidth="1" fill="none"/></>,
  hole:     <><ellipse cx="12" cy="12" rx="10" ry="5" strokeWidth="1.2" fill="none"/><ellipse cx="12" cy="12" rx="6" ry="3" strokeWidth="1" fill="none"/><ellipse cx="12" cy="12" rx="2" ry="1" strokeWidth="1" fill="none"/></>,
  trash:    <><polyline points="3 6 5 6 21 6" strokeWidth="1.3" fill="none" strokeLinecap="round"/><path d="M19 6l-1 14H6L5 6" strokeWidth="1.3" fill="none" strokeLinecap="round" strokeLinejoin="round"/><path d="M10 11v6M14 11v6" strokeWidth="1.2" strokeLinecap="round"/></>,
  check:    <polyline points="20 6 9 17 4 12" strokeWidth="1.8" fill="none" strokeLinecap="round" strokeLinejoin="round"/>,
  clap:     <><path d="M4 3h16a2 2 0 012 2v14a2 2 0 01-2 2H4a2 2 0 01-2-2V5a2 2 0 012-2z" strokeWidth="1.3" fill="none"/><line x1="2" y1="9" x2="22" y2="9" strokeWidth="1.2"/><line x1="7" y1="3" x2="5" y2="9" strokeWidth="1.1"/><line x1="13" y1="3" x2="11" y2="9" strokeWidth="1.1"/><line x1="19" y1="3" x2="17" y2="9" strokeWidth="1.1"/></>,
  grid:     <><rect x="3" y="3" width="7" height="7" strokeWidth="1.2" fill="none"/><rect x="14" y="3" width="7" height="7" strokeWidth="1.2" fill="none"/><rect x="3" y="14" width="7" height="7" strokeWidth="1.2" fill="none"/><rect x="14" y="14" width="7" height="7" strokeWidth="1.2" fill="none"/></>,
  list:     <><line x1="8" y1="6" x2="21" y2="6" strokeWidth="1.3" strokeLinecap="round"/><line x1="8" y1="12" x2="21" y2="12" strokeWidth="1.3" strokeLinecap="round"/><line x1="8" y1="18" x2="21" y2="18" strokeWidth="1.3" strokeLinecap="round"/><line x1="3" y1="6" x2="3.01" y2="6" strokeWidth="1.8" strokeLinecap="round"/><line x1="3" y1="12" x2="3.01" y2="12" strokeWidth="1.8" strokeLinecap="round"/><line x1="3" y1="18" x2="3.01" y2="18" strokeWidth="1.8" strokeLinecap="round"/></>,
  chart:    <><line x1="18" y1="20" x2="18" y2="10" strokeWidth="1.4" strokeLinecap="round"/><line x1="12" y1="20" x2="12" y2="4" strokeWidth="1.4" strokeLinecap="round"/><line x1="6" y1="20" x2="6" y2="14" strokeWidth="1.4" strokeLinecap="round"/></>,
  award:    <><circle cx="12" cy="8" r="6" strokeWidth="1.3" fill="none"/><path d="M8.21 13.89L7 23l5-3 5 3-1.21-9.12" strokeWidth="1.3" fill="none" strokeLinejoin="round"/></>,
  clock:    <><circle cx="12" cy="12" r="9" strokeWidth="1.3" fill="none"/><polyline points="12 7 12 12 15 15" strokeWidth="1.3" fill="none" strokeLinecap="round"/></>,
  info:     <><circle cx="12" cy="12" r="9" strokeWidth="1.3" fill="none"/><line x1="12" y1="8" x2="12" y2="12" strokeWidth="1.4" strokeLinecap="round"/><line x1="12" y1="16" x2="12.01" y2="16" strokeWidth="1.6" strokeLinecap="round"/></>,
  link:     <><path d="M10 13a5 5 0 007.54.54l3-3a5 5 0 00-7.07-7.07l-1.72 1.71" strokeWidth="1.3" fill="none" strokeLinecap="round"/><path d="M14 11a5 5 0 00-7.54-.54l-3 3a5 5 0 007.07 7.07l1.71-1.71" strokeWidth="1.3" fill="none" strokeLinecap="round"/></>,
  users:    <><path d="M17 21v-2a4 4 0 00-4-4H5a4 4 0 00-4 4v2" strokeWidth="1.3" fill="none" strokeLinecap="round"/><circle cx="9" cy="7" r="4" strokeWidth="1.3" fill="none"/><path d="M23 21v-2a4 4 0 00-3-3.87" strokeWidth="1.3" fill="none" strokeLinecap="round"/><path d="M16 3.13a4 4 0 010 7.75" strokeWidth="1.3" fill="none" strokeLinecap="round"/></>,
  tag:      <><path d="M20.59 13.41l-7.17 7.17a2 2 0 01-2.83 0L2 12V2h10l8.59 8.59a2 2 0 010 2.82z" strokeWidth="1.3" fill="none"/><line x1="7" y1="7" x2="7.01" y2="7" strokeWidth="2" strokeLinecap="round"/></>,
};
const Icon=({n,size=16,color="currentColor",cls="",style={}})=>(
  <svg width={size} height={size} viewBox="0 0 24 24" stroke={color} className={cls}
    style={{display:"inline-block",flexShrink:0,verticalAlign:"middle",...style}}>
    {P[n]}
  </svg>
);

// ─── OMDb API ─────────────────────────────────────────────────────────────────
const OMDB="trilogy";
const searchOMDb=async q=>{
  try{const r=await fetch(`https://www.omdbapi.com/?apikey=${OMDB}&s=${encodeURIComponent(q)}&type=movie`);const d=await r.json();return d.Search||[];}catch{return[];}
};
const fetchOMDb=async id=>{
  try{const r=await fetch(`https://www.omdbapi.com/?apikey=${OMDB}&i=${id}&plot=full`);return r.json();}catch{return null;}
};

// ─── Claude AI ────────────────────────────────────────────────────────────────
const ai=async prompt=>{
  const r=await fetch("https://api.anthropic.com/v1/messages",{
    method:"POST",headers:{"Content-Type":"application/json"},
    body:JSON.stringify({model:"claude-sonnet-4-20250514",max_tokens:1200,
      system:"You are a passionate cinephile AI. Return only valid JSON when asked, no markdown fences.",
      messages:[{role:"user",content:prompt}]}),
  });
  const d=await r.json();return d.content?.[0]?.text||"";
};
const safeJSON=(t,fb)=>{try{return JSON.parse(t);}catch{return fb;}};

// ─── DATA ─────────────────────────────────────────────────────────────────────
const SEED=[
  {imdbID:"tt0111161",Title:"The Shawshank Redemption",Year:"1994",Poster:"https://m.media-amazon.com/images/M/MV5BNDE3ODcxYzMtY2YzZC00NmNlLWJiNDMtZDViZWM2MzIxZDYwXkEyXkFqcGdeQXVyNjAwNDUxODI@._V1_SX300.jpg",Genre:"Drama",Director:"Frank Darabont",imdbRating:"9.3",Runtime:"142 min",Actors:"Tim Robbins, Morgan Freeman",mood:"hopeful",watchedDate:"2024-11-12",userRating:5,note:""},
  {imdbID:"tt0068646",Title:"The Godfather",Year:"1972",Poster:"https://m.media-amazon.com/images/M/MV5BM2MyNjYxNmUtYTAwNi00MTYxLWJmNWYtYzZlODY3ZTk3OTFlXkEyXkFqcGdeQXVyNjU0OTQ0OTY@._V1_SX300.jpg",Genre:"Crime, Drama",Director:"Francis Ford Coppola",imdbRating:"9.2",Runtime:"175 min",Actors:"Marlon Brando, Al Pacino",mood:"intense",watchedDate:"2024-10-05",userRating:5,note:""},
  {imdbID:"tt0108052",Title:"Schindler's List",Year:"1993",Poster:"https://m.media-amazon.com/images/M/MV5BNDE4OTEyMzUtNzc1Ni00MmZmLTk0NmItYTgxZGRjYTIxYjNiXkEyXkFqcGdeQXVyNjU0OTQ0OTY@._V1_SX300.jpg",Genre:"Biography, Drama",Director:"Steven Spielberg",imdbRating:"9.0",Runtime:"195 min",Actors:"Liam Neeson, Ralph Fiennes",mood:"reflective",watchedDate:"2024-09-20",userRating:5,note:""},
  {imdbID:"tt0137523",Title:"Fight Club",Year:"1999",Poster:"https://m.media-amazon.com/images/M/MV5BMmEzNTkxYjQtZTc0MC00YTVjLTg5ZTEtZWMwOWVlYzY0NWIwXkEyXkFqcGdeQXVyNjU0OTQ0OTY@._V1_SX300.jpg",Genre:"Drama",Director:"David Fincher",imdbRating:"8.8",Runtime:"139 min",Actors:"Brad Pitt, Edward Norton",mood:"restless",watchedDate:"2024-08-14",userRating:4,note:""},
  {imdbID:"tt0816692",Title:"Interstellar",Year:"2014",Poster:"https://m.media-amazon.com/images/M/MV5BZjdkOTU3MDktN2IxOS00OGEyLWFmMjktY2FiMmZkNWIyODZiXkEyXkFqcGdeQXVyMTMxODk2OTU@._V1_SX300.jpg",Genre:"Adventure, Sci-Fi",Director:"Christopher Nolan",imdbRating:"8.7",Runtime:"169 min",Actors:"Matthew McConaughey, Anne Hathaway",mood:"wonder",watchedDate:"2024-07-30",userRating:5,note:""},
  {imdbID:"tt0120737",Title:"The Lord of the Rings: The Fellowship of the Ring",Year:"2001",Poster:"https://m.media-amazon.com/images/M/MV5BN2EyZjM3NzUtNWUzMi00MTgxLWI0NTctMzY4M2VlOTdjZWRiXkEyXkFqcGdeQXVyNDUzOTQ5MjY@._V1_SX300.jpg",Genre:"Adventure, Fantasy",Director:"Peter Jackson",imdbRating:"8.8",Runtime:"178 min",Actors:"Elijah Wood, Ian McKellen",mood:"wonder",watchedDate:"2024-06-10",userRating:5,note:""},
  {imdbID:"tt0317248",Title:"City of God",Year:"2002",Poster:"https://m.media-amazon.com/images/M/MV5BOTMwYjc5ZmItYTFjZC00ZGQ3LTlkNTMtMjZiYjgxNDc3MTUyXkEyXkFqcGdeQXVyNzkwMjQ5NzM@._V1_SX300.jpg",Genre:"Crime, Drama",Director:"Fernando Meirelles",imdbRating:"8.6",Runtime:"130 min",Actors:"Alexandre Rodrigues, Leandro Firmino",mood:"intense",watchedDate:"2024-05-22",userRating:5,note:""},
  {imdbID:"tt0245429",Title:"Spirited Away",Year:"2001",Poster:"https://m.media-amazon.com/images/M/MV5BMjlmZmI5MDctNDE2YS00YWE0LWE5ZWItZDBhYWQ0NTcxNWRhXkEyXkFqcGdeQXVyMTMxODk2OTU@._V1_SX300.jpg",Genre:"Animation, Adventure",Director:"Hayao Miyazaki",imdbRating:"8.6",Runtime:"125 min",Actors:"Daveigh Chase, Suzanne Pleshette",mood:"wonder",watchedDate:"2024-04-15",userRating:5,note:""},
];

const MOODS=["hopeful","intense","reflective","restless","wonder","melancholic","joyful","thrilled","cozy","haunted"];
const MC={hopeful:"#c49a38",intense:"#a84038",reflective:"#6c5ea0",restless:"#b06830",wonder:"#3a8898",melancholic:"#4c5a9a",joyful:"#3a8458",thrilled:"#a83870",cozy:"#8868b4",haunted:"#5a6a6a"};
const MOOD_EMOJI={hopeful:"☀",intense:"⚡",reflective:"🪞",restless:"🌪",wonder:"✨",melancholic:"🌧",joyful:"🌸",thrilled:"🔥",cozy:"🍂",haunted:"🌑"};

// ─── STYLE TOKENS ─────────────────────────────────────────────────────────────
const OV ={position:"fixed",inset:0,background:"rgba(10,8,5,.87)",zIndex:900,display:"flex",alignItems:"center",justifyContent:"center",backdropFilter:"blur(8px)"};
const BG ={background:"var(--gold)",color:"var(--bg)",border:"none",padding:"10px 20px",fontSize:"11px",letterSpacing:"2px",cursor:"pointer",borderRadius:"4px",fontFamily:"var(--sans)",display:"flex",alignItems:"center",gap:"7px",fontWeight:"500"};
const BO ={background:"transparent",color:"var(--gold)",border:"1px solid var(--border2)",padding:"9px 18px",fontSize:"11px",letterSpacing:"2px",cursor:"pointer",borderRadius:"4px",fontFamily:"var(--sans)",display:"flex",alignItems:"center",gap:"7px"};
const tB ={background:"var(--gold)",color:"var(--bg)",border:"none",padding:"4px 10px",fontSize:"10px",letterSpacing:"1px",cursor:"pointer",borderRadius:"3px",fontFamily:"var(--sans)",display:"flex",alignItems:"center",gap:"4px"};

function Spin({color="var(--gold)",size=14}){return <div className="hspin" style={{width:size,height:size,border:`1.5px solid ${color}`,borderTopColor:"transparent",borderRadius:"50%",flexShrink:0}}/>;}
function Empty({n,text}){return <div style={{display:"flex",flexDirection:"column",alignItems:"center",justifyContent:"center",padding:"80px 0",gap:"16px"}}><Icon n={n} size={44} color="var(--border2)"/><div style={{fontFamily:"var(--serif)",fontSize:"15px",color:"var(--text3)",fontStyle:"italic"}}>{text}</div></div>;}

// ─── STAR RATING ──────────────────────────────────────────────────────────────
function Stars({value=0,onChange,size=14}){
  const [hover,setHover]=useState(0);
  return(
    <div style={{display:"flex",gap:"2px"}}>
      {[1,2,3,4,5].map(i=>(
        <button key={i} onClick={()=>onChange&&onChange(i)} onMouseEnter={()=>setHover(i)} onMouseLeave={()=>setHover(0)}
          style={{background:"none",border:"none",cursor:onChange?"pointer":"default",padding:"1px",color:(hover||value)>=i?"#c49a38":"var(--text4)"}}>
          <Icon n={(hover||value)>=i?"starFill":"star"} size={size} color={(hover||value)>=i?"#c49a38":"var(--text4)"}/>
        </button>
      ))}
    </div>
  );
}

// ─── MAIN APP ─────────────────────────────────────────────────────────────────
export default function App(){
  const [tab,setTab]=useState("vault");
  const [watched,setWatched]=useState(SEED);
  const [watchlist,setWatchlist]=useState([]);
  const [q,setQ]=useState("");
  const [results,setResults]=useState([]);
  const [searching,setSearching]=useState(false);
  const [detailM,setDetailM]=useState(null);
  const [detailD,setDetailD]=useState(null);
  const [detailLoading,setDetailLoading]=useState(false);
  const [moodFor,setMoodFor]=useState(null);
  const [ratingFor,setRatingFor]=useState(null);
  const [trivia,setTrivia]=useState(null);
  const [triviaL,setTriviaL]=useState(false);
  const [rabbit,setRabbit]=useState(null);
  const [rabbitL,setRabbitL]=useState(false);
  const [seance,setSeance]=useState({step:"idle",mood:"",recs:[]});
  const [dna,setDna]=useState(null);
  const [dnaL,setDnaL]=useState(false);
  const [discover,setDiscover]=useState([]);
  const [discoverL,setDiscoverL]=useState(false);
  const [toast,setToast]=useState(null);
  const [viewMode,setViewMode]=useState("grid"); // grid | list
  const [sortBy,setSortBy]=useState("recent"); // recent | rating | title | year
  const [filterMood,setFilterMood]=useState(null);
  const [stats,setStats]=useState(null);
  const timer=useRef(null);

  const toast$=(msg,type="ok")=>{setToast({msg,type});setTimeout(()=>setToast(null),3000);};

  // ── Search debounce ──
  useEffect(()=>{
    if(!q.trim()){setResults([]);return;}
    clearTimeout(timer.current);
    timer.current=setTimeout(async()=>{setSearching(true);const r=await searchOMDb(q);setResults(r.slice(0,8));setSearching(false);},360);
  },[q]);

  // ── Open detail (live OMDb fetch) ──
  const openDetail=async m=>{
    setDetailM(m);setDetailD(null);setDetailLoading(true);
    const d=await fetchOMDb(m.imdbID);
    setDetailD(d);setDetailLoading(false);
  };
  const closeDetail=()=>{setDetailM(null);setDetailD(null);};

  // ── Vault actions ──
  const addWatched=(m,mood,rating=0)=>{
    if(watched.find(x=>x.imdbID===m.imdbID)){toast$("Already in your vault","info");return;}
    const entry={...m,mood,userRating:rating,note:"",watchedDate:new Date().toISOString().split("T")[0]};
    setWatched(p=>[entry,...p]);
    setWatchlist(p=>p.filter(x=>x.imdbID!==m.imdbID));
    toast$(`"${m.Title}" added to vault`);
    setMoodFor(null);setRatingFor(null);
  };

  const updateRating=(imdbID,r)=>{
    setWatched(p=>p.map(m=>m.imdbID===imdbID?{...m,userRating:r}:m));
  };
  const updateNote=(imdbID,note)=>{
    setWatched(p=>p.map(m=>m.imdbID===imdbID?{...m,note}:m));
  };
  const removeWatched=m=>{
    setWatched(p=>p.filter(x=>x.imdbID!==m.imdbID));
    toast$(`"${m.Title}" removed from vault`,"info");
  };

  const addWatchlist=m=>{
    if(watchlist.find(x=>x.imdbID===m.imdbID)||watched.find(x=>x.imdbID===m.imdbID)){toast$("Already saved","info");return;}
    setWatchlist(p=>[{...m,addedDate:new Date().toISOString().split("T")[0]},...p]);
    toast$(`"${m.Title}" added to watchlist`);
  };
  const removeWatchlist=m=>{setWatchlist(p=>p.filter(x=>x.imdbID!==m.imdbID));};

  // ── AI features ──
  const fetchTrivia=async m=>{
    setTriviaL(true);setTrivia(null);
    const t=await ai(`Little-known fascinating trivia about "${m.Title}" (${m.Year}). JSON: {"fact":"...","category":"Behind the Scenes|Cultural Impact|Hidden Detail|Cast Secret|Director's Vision|Box Office","mindblown":true,"movie":"${m.Title}"}`);
    setTrivia(safeJSON(t,{fact:`${m.Title} changed cinema in ways still being discovered.`,category:"Cultural Impact",mindblown:false,movie:m.Title}));
    setTriviaL(false);
  };
  const fetchRabbit=async m=>{
    setRabbitL(true);setRabbit(null);
    const t=await ai(`"Rabbit Hole" from "${m.Title}": 3 increasingly obscure films linked by one hidden cinematic thread. JSON: {"thread":"the secret connection","films":[{"title":"...","year":"...","connection":"...","obscurity":5}]}`);
    const d=safeJSON(t,null);
    setRabbit(d?{...d,origin:m.Title}:null);
    setRabbitL(false);
  };
  const runSeance=async mood=>{
    setSeance({step:"loading",mood,recs:[]});
    const titles=watched.map(m=>m.Title).join(", ");
    const t=await ai(`Cinephile who loved: ${titles} — feeling "${mood}". 4 perfect films for this emotional state. JSON array: [{"title":"...","year":"...","why":"one sentence pairing their taste AND mood","obscurityScore":5}]`);
    setSeance({step:"results",mood,recs:safeJSON(t,[])});
  };
  const genDNA=async()=>{
    setDnaL(true);setDna(null);
    const films=watched.map(m=>`${m.Title}(${m.Year}) dir.${m.Director||"?"}`).join(";");
    const t=await ai(`Cinema DNA for: ${films}. JSON: {"archetype":"poetic title e.g. 'Baroque Nihilist'","dnaStrands":[{"label":"...","score":72,"color":"#hex"}] (exactly 5 strands),"directorSoul":"director name","era":"e.g. 1970s","blindspot":"genre or era they've missed","verdict":"2 evocative sentences"}`);
    setDna(safeJSON(t,null));
    setDnaL(false);
  };
  const loadDiscover=async()=>{
    setDiscoverL(true);
    const titles=watched.slice(0,7).map(m=>m.Title).join(", ");
    const t=await ai(`Based on loving: ${titles} — 6 hidden gem films with obscurity score >6. JSON array: [{"title":"...","year":"...","director":"...","pitch":"one electrifying sentence","vibe":"2-3 word vibe","obscurityScore":7}]`);
    setDiscover(safeJSON(t,[]));
    setDiscoverL(false);
  };

  // ── Stats computation ──
  useEffect(()=>{
    if(!watched.length){setStats(null);return;}
    const genres={},directors={},decades={},moods={};
    let totalRuntime=0,ratingSum=0,ratingCount=0;
    watched.forEach(m=>{
      (m.Genre||"").split(",").forEach(g=>{const k=g.trim();if(k)genres[k]=(genres[k]||0)+1;});
      if(m.Director)directors[m.Director]=(directors[m.Director]||0)+1;
      const dec=Math.floor((parseInt(m.Year)||0)/10)*10;if(dec>1900)decades[dec]=(decades[dec]||0)+1;
      if(m.mood)moods[m.mood]=(moods[m.mood]||0)+1;
      const rt=parseInt(m.Runtime);if(!isNaN(rt))totalRuntime+=rt;
      if(m.userRating){ratingSum+=m.userRating;ratingCount++;}
    });
    const topGenres=Object.entries(genres).sort((a,b)=>b[1]-a[1]).slice(0,5);
    const topDirectors=Object.entries(directors).sort((a,b)=>b[1]-a[1]).slice(0,3);
    const topDecade=Object.entries(decades).sort((a,b)=>b[1]-a[1])[0];
    const topMood=Object.entries(moods).sort((a,b)=>b[1]-a[1])[0];
    setStats({topGenres,topDirectors,topDecade,topMood,totalRuntime,avgRating:ratingCount?ratingSum/ratingCount:0,totalFilms:watched.length});
  },[watched]);

  useEffect(()=>{if(tab==="discover"&&!discover.length)loadDiscover();},[tab]);
  useEffect(()=>{if(tab==="dna"&&!dna&&!dnaL)genDNA();},[tab]);

  // ── Sorted/filtered vault ──
  const sortedWatched=useCallback(()=>{
    let films=filterMood?watched.filter(m=>m.mood===filterMood):[...watched];
    if(sortBy==="rating")films.sort((a,b)=>(b.userRating||0)-(a.userRating||0));
    else if(sortBy==="title")films.sort((a,b)=>a.Title.localeCompare(b.Title));
    else if(sortBy==="year")films.sort((a,b)=>(parseInt(b.Year)||0)-(parseInt(a.Year)||0));
    else films.sort((a,b)=>b.watchedDate?.localeCompare(a.watchedDate||"")||0);
    return films;
  },[watched,filterMood,sortBy]);

  const TABS=[
    {id:"vault",icon:"film",label:"Vault"},
    {id:"watchlist",icon:"bookmark",label:"Watchlist"},
    {id:"stats",icon:"chart",label:"Stats"},
    {id:"seance",icon:"moon",label:"Séance"},
    {id:"dna",icon:"dna",label:"DNA"},
    {id:"discover",icon:"compass",label:"Discover"},
  ];

  return(
    <div style={{minHeight:"100vh",display:"flex",flexDirection:"column",background:"var(--bg)"}}>

      {/* Toast */}
      {toast&&<div className="fadeUp" style={{position:"fixed",top:"18px",right:"18px",zIndex:9999,background:toast.type==="ok"?"var(--gold)":"var(--bg4)",color:toast.type==="ok"?"var(--bg)":"var(--text2)",padding:"9px 18px",borderRadius:"4px",fontFamily:"var(--sans)",fontSize:"11px",letterSpacing:"1.5px",boxShadow:"0 6px 28px rgba(0,0,0,.5)"}}>{toast.msg}</div>}

      {/* Header */}
      <header style={{display:"flex",alignItems:"center",gap:"20px",padding:"14px 30px",borderBottom:"1px solid var(--border)",background:"var(--bg2)",position:"sticky",top:0,zIndex:300}}>
        {/* Logo */}
        <div style={{display:"flex",alignItems:"center",gap:"10px",flexShrink:0}}>
          <Icon n="clap" size={20} color="var(--gold)"/>
          <div>
            <div style={{fontFamily:"var(--display)",fontSize:"14px",letterSpacing:"5px"}}>CINÉMATHÈQUE</div>
            <div style={{fontFamily:"var(--sans)",fontSize:"8px",letterSpacing:"4px",color:"var(--text3)",marginTop:"1px"}}>PERSONELLE</div>
          </div>
        </div>

        {/* OMDb Search */}
        <div style={{position:"relative",flex:1,maxWidth:"440px",margin:"0 auto"}}>
          <Icon n="search" size={13} color="var(--text3)" style={{position:"absolute",left:"13px",top:"50%",transform:"translateY(-50%)",pointerEvents:"none"}}/>
          {searching?<Spin size={13} color="var(--gold)"/> && <div style={{position:"absolute",right:"13px",top:"50%",transform:"translateY(-50%)"}}><Spin size={13}/></div>:null}
          <input value={q} onChange={e=>setQ(e.target.value)}
            placeholder="Search 500,000+ films via OMDb…"
            style={{width:"100%",background:"var(--bg3)",border:"1px solid var(--border)",borderRadius:"4px",padding:"9px 14px 9px 37px",color:"var(--text)",fontFamily:"var(--sans)",fontSize:"13px",transition:"border-color .2s"}}/>

          {/* OMDb results dropdown */}
          {results.length>0&&(
            <div style={{position:"absolute",top:"calc(100% + 6px)",left:0,right:0,background:"var(--bg3)",border:"1px solid var(--border2)",borderRadius:"6px",zIndex:600,boxShadow:"0 20px 56px rgba(0,0,0,.6)",overflow:"hidden"}}>
              <div style={{padding:"8px 14px 6px",fontFamily:"var(--sans)",fontSize:"9px",letterSpacing:"2.5px",color:"var(--text3)",borderBottom:"1px solid var(--border)"}}>
                OMDB RESULTS — {results.length} FILMS FOUND
              </div>
              {results.map(m=>(
                <div key={m.imdbID} onClick={()=>{openDetail(m);setQ("");setResults([]);}}
                  style={{display:"flex",alignItems:"center",gap:"12px",padding:"9px 14px",cursor:"pointer",borderBottom:"1px solid var(--border3)",transition:"background .12s"}}
                  onMouseEnter={e=>e.currentTarget.style.background="var(--bg4)"}
                  onMouseLeave={e=>e.currentTarget.style.background="transparent"}>
                  <img src={m.Poster!=="N/A"?m.Poster:"https://via.placeholder.com/28x42/221e16/c8a96e?text=?"} style={{width:"28px",height:"42px",objectFit:"cover",borderRadius:"2px",flexShrink:0}}/>
                  <div style={{flex:1,minWidth:0}}>
                    <div style={{fontFamily:"var(--serif)",fontSize:"14px",whiteSpace:"nowrap",overflow:"hidden",textOverflow:"ellipsis"}}>{m.Title}</div>
                    <div style={{fontFamily:"var(--sans)",fontSize:"10px",color:"var(--text3)",letterSpacing:"1px",marginTop:"1px"}}>{m.Year} · {m.Type}</div>
                  </div>
                  <div style={{display:"flex",gap:"5px",flexShrink:0}}>
                    <button className="hbtn" onClick={e=>{e.stopPropagation();setMoodFor(m);setQ("");setResults([]);}} style={tB}><Icon n="plus" size={10} color="var(--bg)"/>Vault</button>
                    <button className="hbtn" onClick={e=>{e.stopPropagation();addWatchlist(m);setQ("");setResults([]);}} style={{...tB,background:"transparent",border:"1px solid var(--border2)",color:"var(--gold)"}}><Icon n="bookmark" size={10} color="var(--gold)"/>List</button>
                  </div>
                </div>
              ))}
            </div>
          )}
        </div>

        {/* Stats pill */}
        <div style={{display:"flex",alignItems:"center",gap:"16px",flexShrink:0}}>
          <div style={{display:"flex",alignItems:"center",gap:"8px",background:"var(--bg3)",border:"1px solid var(--border)",borderRadius:"20px",padding:"6px 14px"}}>
            <Icon n="film" size={12} color="var(--gold)"/>
            <span style={{fontFamily:"var(--sans)",fontSize:"11px",color:"var(--gold)",letterSpacing:"1px"}}>{watched.length}</span>
            <span style={{fontFamily:"var(--sans)",fontSize:"10px",color:"var(--text3)"}}>SEEN</span>
            <span style={{color:"var(--text4)",fontSize:"12px",margin:"0 2px"}}>·</span>
            <Icon n="bookmark" size={12} color="var(--teal)"/>
            <span style={{fontFamily:"var(--sans)",fontSize:"11px",color:"var(--teal)",letterSpacing:"1px"}}>{watchlist.length}</span>
            <span style={{fontFamily:"var(--sans)",fontSize:"10px",color:"var(--text3)"}}>QUEUED</span>
          </div>
        </div>
      </header>

      {/* Nav */}
      <nav style={{display:"flex",borderBottom:"1px solid var(--border)",background:"var(--bg2)",padding:"0 30px",overflowX:"auto"}}>
        {TABS.map(t=>(
          <button key={t.id} onClick={()=>setTab(t.id)}
            style={{display:"flex",alignItems:"center",gap:"7px",background:"none",border:"none",borderBottom:tab===t.id?"2px solid var(--gold)":"2px solid transparent",color:tab===t.id?"var(--gold)":"var(--text3)",padding:"11px 16px",cursor:"pointer",fontFamily:"var(--sans)",fontSize:"10px",letterSpacing:"2.5px",marginBottom:"-1px",transition:"all .18s",whiteSpace:"nowrap"}}>
            <Icon n={t.icon} size={13} color={tab===t.id?"var(--gold)":"var(--text3)"}/>
            {t.label.toUpperCase()}
          </button>
        ))}
      </nav>

      {/* Mood picker overlay */}
      {moodFor&&(
        <div style={OV} onClick={()=>setMoodFor(null)}>
          <div className="popIn" style={{background:"var(--bg3)",border:"1px solid var(--border2)",borderRadius:"10px",padding:"32px",maxWidth:"480px",width:"92%",boxShadow:"0 28px 80px rgba(0,0,0,.7)"}} onClick={e=>e.stopPropagation()}>
            <div style={{fontFamily:"var(--display)",fontSize:"22px",fontStyle:"italic",marginBottom:"4px"}}>How did it make you feel?</div>
            <div style={{fontFamily:"var(--serif)",fontSize:"16px",color:"var(--gold)",marginBottom:"6px",fontStyle:"italic"}}>"{moodFor.Title}"</div>
            <div style={{fontFamily:"var(--sans)",fontSize:"11px",color:"var(--text3)",marginBottom:"24px",letterSpacing:"0.5px"}}>Tag the emotional register of this film for your vault.</div>
            <div style={{display:"grid",gridTemplateColumns:"repeat(5,1fr)",gap:"8px",marginBottom:"24px"}}>
              {MOODS.map(m=>(
                <button key={m} className="hbtn" onClick={()=>setRatingFor({...moodFor,_mood:m})}
                  style={{background:MC[m]+"18",border:`1px solid ${MC[m]}44`,borderRadius:"5px",padding:"10px 4px",color:MC[m],fontFamily:"var(--sans)",fontSize:"10px",letterSpacing:"1px",cursor:"pointer",textTransform:"uppercase",display:"flex",flexDirection:"column",alignItems:"center",gap:"4px"}}>
                  <span style={{fontSize:"18px"}}>{MOOD_EMOJI[m]}</span>
                  {m}
                </button>
              ))}
            </div>
          </div>
        </div>
      )}

      {/* Rating picker overlay */}
      {ratingFor&&(
        <div style={OV} onClick={()=>setRatingFor(null)}>
          <div className="popIn" style={{background:"var(--bg3)",border:"1px solid var(--border2)",borderRadius:"10px",padding:"32px",maxWidth:"380px",width:"92%",boxShadow:"0 28px 80px rgba(0,0,0,.7)",textAlign:"center"}} onClick={e=>e.stopPropagation()}>
            <div style={{fontFamily:"var(--display)",fontSize:"20px",fontStyle:"italic",marginBottom:"4px"}}>Rate it.</div>
            <div style={{fontFamily:"var(--serif)",fontSize:"15px",color:"var(--gold)",marginBottom:"24px",fontStyle:"italic"}}>"{ratingFor.Title}"</div>
            <div style={{display:"flex",justifyContent:"center",gap:"4px",marginBottom:"28px"}}>
              {[1,2,3,4,5].map(i=>(
                <button key={i} onClick={()=>addWatched(ratingFor,ratingFor._mood,i)}
                  style={{background:"none",border:"none",cursor:"pointer",padding:"4px",color:"#c49a38",fontSize:"32px"}}>★</button>
              ))}
            </div>
            <button onClick={()=>addWatched(ratingFor,ratingFor._mood,0)} style={{...BO,justifyContent:"center",width:"100%",fontSize:"10px",letterSpacing:"2px"}}>Skip rating</button>
          </div>
        </div>
      )}

      {/* Detail modal */}
      {detailM&&(
        <div style={OV} onClick={closeDetail}>
          <div className="popIn" style={{background:"var(--bg3)",border:"1px solid var(--border)",borderRadius:"10px",padding:"32px",maxWidth:"660px",width:"92%",maxHeight:"88vh",overflowY:"auto",boxShadow:"0 28px 80px rgba(0,0,0,.7)",position:"relative"}} onClick={e=>e.stopPropagation()}>
            <button onClick={closeDetail} style={{position:"absolute",top:"16px",right:"16px",background:"var(--bg4)",border:"1px solid var(--border)",borderRadius:"50%",width:"32px",height:"32px",display:"flex",alignItems:"center",justifyContent:"center",cursor:"pointer"}}><Icon n="x" size={14} color="var(--text3)"/></button>
            <div style={{display:"flex",gap:"26px"}}>
              {detailLoading?(
                <div className="skeleton" style={{width:"130px",height:"195px",borderRadius:"4px",flexShrink:0}}/>
              ):(
                <img src={detailD?.Poster&&detailD.Poster!=="N/A"?detailD.Poster:detailM.Poster!=="N/A"?detailM.Poster:"https://via.placeholder.com/130x195/221e16/c8a96e?text=?"} style={{width:"130px",height:"195px",objectFit:"cover",borderRadius:"5px",flexShrink:0,border:"1px solid var(--border)"}}/>
              )}
              <div style={{flex:1}}>
                <div style={{fontFamily:"var(--display)",fontSize:"22px",lineHeight:"1.2",marginBottom:"8px"}}>{detailD?.Title||detailM.Title}</div>
                <div style={{fontFamily:"var(--sans)",fontSize:"10px",letterSpacing:"2px",color:"var(--text3)",marginBottom:"6px"}}>{detailD?.Year} · {detailD?.Runtime} · {detailD?.Rated} · {detailD?.Genre}</div>
                <div style={{fontFamily:"var(--serif)",fontSize:"13px",color:"var(--gold)",marginBottom:"6px",fontStyle:"italic"}}>dir. {detailD?.Director||"—"}</div>
                {detailD?.imdbRating&&<div style={{display:"flex",alignItems:"center",gap:"6px",marginBottom:"6px"}}><Icon n="starFill" size={13} color="#c49a38"/><span style={{fontFamily:"var(--sans)",fontSize:"12px",color:"#c49a38",letterSpacing:"1px"}}>{detailD.imdbRating}/10</span><span style={{fontFamily:"var(--sans)",fontSize:"10px",color:"var(--text3)"}}>{detailD?.imdbVotes&&`(${detailD.imdbVotes} votes)`}</span></div>}
                {detailD?.Awards&&detailD.Awards!=="N/A"&&<div style={{display:"flex",alignItems:"center",gap:"6px",marginBottom:"10px"}}><Icon n="award" size={12} color="var(--gold)"/><span style={{fontFamily:"var(--sans)",fontSize:"10px",color:"var(--text3)",letterSpacing:"0.3px"}}>{detailD.Awards}</span></div>}
                <div style={{fontFamily:"var(--serif)",fontSize:"14px",color:"var(--text2)",lineHeight:"1.75",fontStyle:"italic",marginBottom:"12px"}}>{detailLoading?"Loading…":detailD?.Plot||"No plot available."}</div>
                {detailD?.Actors&&<div style={{fontFamily:"var(--sans)",fontSize:"11px",color:"var(--text3)",marginBottom:"6px",letterSpacing:"0.3px"}}><strong style={{color:"var(--text4)"}}>Cast</strong> — {detailD.Actors}</div>}
                {detailD?.Language&&<div style={{fontFamily:"var(--sans)",fontSize:"11px",color:"var(--text3)",marginBottom:"20px",letterSpacing:"0.3px"}}><strong style={{color:"var(--text4)"}}>Language</strong> — {detailD.Language} · <strong style={{color:"var(--text4)"}}>Country</strong> — {detailD.Country}</div>}
                <div style={{display:"flex",gap:"10px"}}>
                  <button className="hbtn" onClick={()=>{setMoodFor(detailM);closeDetail();}} style={BG}><Icon n="plus" size={12} color="var(--bg)"/>Add to Vault</button>
                  <button className="hbtn" onClick={()=>addWatchlist(detailM)} style={BO}><Icon n="bookmark" size={12} color="var(--gold)"/>Watchlist</button>
                </div>
              </div>
            </div>
          </div>
        </div>
      )}

      {/* Content */}
      <main style={{flex:1,padding:"26px 30px 64px"}}>
        {tab==="vault"&&<VaultTab watched={sortedWatched()} allWatched={watched} filterMood={filterMood} setFilterMood={setFilterMood} sortBy={sortBy} setSortBy={setSortBy} viewMode={viewMode} setViewMode={setViewMode} trivia={trivia} triviaL={triviaL} onTrivia={fetchTrivia} rabbit={rabbit} rabbitL={rabbitL} onRabbit={fetchRabbit} onOpen={openDetail} onRemove={removeWatched} onRating={updateRating} onNote={updateNote}/>}
        {tab==="watchlist"&&<WatchlistTab watchlist={watchlist} onMark={m=>setMoodFor(m)} onRemove={removeWatchlist} onOpen={openDetail}/>}
        {tab==="stats"&&<StatsTab stats={stats} watched={watched}/>}
        {tab==="seance"&&<SeanceTab seance={seance} onMood={runSeance} onAdd={addWatchlist}/>}
        {tab==="dna"&&<DNATab dna={dna} loading={dnaL} onRegen={genDNA}/>}
        {tab==="discover"&&<DiscoverTab recs={discover} loading={discoverL} onAdd={addWatchlist} onOpen={openDetail} onRefresh={loadDiscover}/>}
      </main>
    </div>
  );
}

// ─── VAULT TAB ────────────────────────────────────────────────────────────────
function VaultTab({watched,allWatched,filterMood,setFilterMood,sortBy,setSortBy,viewMode,setViewMode,trivia,triviaL,onTrivia,rabbit,rabbitL,onRabbit,onOpen,onRemove,onRating,onNote}){
  return(
    <div>
      {/* Toolbar */}
      <div style={{display:"flex",flexWrap:"wrap",gap:"10px",alignItems:"center",marginBottom:"20px"}}>
        {/* Mood filter */}
        <div style={{display:"flex",flexWrap:"wrap",gap:"6px",flex:1}}>
          <button onClick={()=>setFilterMood(null)} style={{background:!filterMood?"var(--bg4)":"transparent",border:`1px solid ${!filterMood?"var(--border2)":"var(--border)"}`,borderRadius:"20px",padding:"4px 14px",fontFamily:"var(--sans)",fontSize:"10px",letterSpacing:"1.5px",cursor:"pointer",color:!filterMood?"var(--gold)":"var(--text3)",transition:"all .15s"}}>
            ALL <span style={{opacity:.5,fontSize:"9px"}}>{allWatched.length}</span>
          </button>
          {MOODS.filter(m=>allWatched.some(w=>w.mood===m)).map(m=>(
            <button key={m} onClick={()=>setFilterMood(m===filterMood?null:m)}
              style={{background:filterMood===m?MC[m]+"1c":"transparent",border:`1px solid ${MC[m]+(filterMood===m?"88":"2a")}`,borderRadius:"20px",padding:"4px 12px",fontFamily:"var(--sans)",fontSize:"10px",letterSpacing:"1px",cursor:"pointer",color:MC[m]+(filterMood===m?"":"88"),textTransform:"uppercase",transition:"all .15s"}}>
              {MOOD_EMOJI[m]} {m}
            </button>
          ))}
        </div>
        {/* Sort */}
        <select value={sortBy} onChange={e=>setSortBy(e.target.value)} style={{background:"var(--bg3)",border:"1px solid var(--border)",borderRadius:"4px",padding:"5px 10px",color:"var(--text3)",fontFamily:"var(--sans)",fontSize:"10px",letterSpacing:"1.5px",cursor:"pointer"}}>
          <option value="recent">RECENT FIRST</option>
          <option value="rating">MY RATING</option>
          <option value="title">TITLE A–Z</option>
          <option value="year">YEAR</option>
        </select>
        {/* View mode */}
        <div style={{display:"flex",background:"var(--bg3)",border:"1px solid var(--border)",borderRadius:"4px",overflow:"hidden"}}>
          {[["grid","grid"],["list","list"]].map(([m,icon])=>(
            <button key={m} onClick={()=>setViewMode(m)} style={{background:viewMode===m?"var(--bg5)":"transparent",border:"none",padding:"6px 10px",cursor:"pointer",display:"flex",alignItems:"center"}}>
              <Icon n={icon} size={13} color={viewMode===m?"var(--gold)":"var(--text3)"}/>
            </button>
          ))}
        </div>
      </div>

      {/* Trivia card */}
      {(trivia||triviaL)&&(
        <div className="slideIn" style={{background:"var(--bg2)",border:"1px solid var(--border)",borderLeft:"3px solid var(--gold)",borderRadius:"6px",padding:"18px 22px",marginBottom:"18px"}}>
          {triviaL?<div style={{display:"flex",alignItems:"center",gap:"10px",color:"var(--text3)",fontFamily:"var(--sans)",fontSize:"11px",letterSpacing:"2px"}}><Spin/>UNEARTHING A SECRET…</div>:
            <><div style={{display:"flex",alignItems:"center",gap:"8px",marginBottom:"7px"}}><Icon n="sparkle" size={13} color="var(--gold)"/><span style={{fontFamily:"var(--sans)",fontSize:"10px",letterSpacing:"2.5px",color:"var(--gold)"}}>{trivia.category?.toUpperCase()}</span>{trivia.mindblown&&<span style={{fontFamily:"var(--sans)",fontSize:"10px",color:"var(--red)",marginLeft:"4px"}}>· MIND-BLOWING</span>}</div>
            <div style={{fontFamily:"var(--display)",fontSize:"14px",fontStyle:"italic",marginBottom:"7px"}}>{trivia.movie}</div>
            <div style={{fontFamily:"var(--serif)",fontSize:"16px",color:"var(--text2)",lineHeight:"1.72",fontStyle:"italic"}}>{trivia.fact}</div></>
          }
        </div>
      )}

      {/* Rabbit hole card */}
      {(rabbit||rabbitL)&&(
        <div className="slideIn" style={{background:"var(--bg2)",border:"1px solid var(--border)",borderLeft:"3px solid var(--teal)",borderRadius:"6px",padding:"18px 22px",marginBottom:"18px"}}>
          {rabbitL?<div style={{display:"flex",alignItems:"center",gap:"10px",color:"var(--text3)",fontFamily:"var(--sans)",fontSize:"11px",letterSpacing:"2px"}}><Spin color="var(--teal)"/>DIGGING THE RABBIT HOLE…</div>:
            <><div style={{display:"flex",alignItems:"center",gap:"8px",marginBottom:"6px"}}><Icon n="hole" size={14} color="var(--teal)"/><span style={{fontFamily:"var(--sans)",fontSize:"10px",letterSpacing:"2.5px",color:"var(--teal)"}}>RABBIT HOLE</span></div>
            <div style={{fontFamily:"var(--display)",fontSize:"14px",fontStyle:"italic",marginBottom:"4px"}}>From <em style={{color:"var(--gold)"}}>{rabbit.origin}</em></div>
            <div style={{fontFamily:"var(--sans)",fontSize:"11px",color:"var(--text3)",marginBottom:"16px",letterSpacing:"0.8px"}}>Thread: {rabbit.thread}</div>
            {rabbit.films?.map((f,i)=>(
              <div key={i} style={{display:"flex",gap:"12px",alignItems:"flex-start",marginBottom:"12px"}}>
                <div style={{fontFamily:"var(--display)",fontSize:"26px",color:"var(--teal)",opacity:.2,lineHeight:1,flexShrink:0,width:"22px"}}>{i+1}</div>
                <div>
                  <div style={{fontFamily:"var(--serif)",fontSize:"15px",marginBottom:"2px"}}>{f.title} <span style={{color:"var(--text3)",fontSize:"13px"}}>({f.year})</span></div>
                  <div style={{fontFamily:"var(--serif)",fontSize:"13px",color:"var(--text2)",fontStyle:"italic",marginBottom:"4px"}}>{f.connection}</div>
                  <div style={{display:"flex",alignItems:"center",gap:"3px"}}>
                    {Array.from({length:10}).map((_,j)=><div key={j} style={{width:"9px",height:"3px",borderRadius:"2px",background:j<f.obscurity?"var(--teal)":"var(--bg4)"}}/>)}
                    <span style={{fontFamily:"var(--sans)",fontSize:"10px",color:"var(--teal)",marginLeft:"6px"}}>obscurity {f.obscurity}/10</span>
                  </div>
                </div>
              </div>
            ))}</>
          }
        </div>
      )}

      {/* Grid or list */}
      {viewMode==="grid"?(
        <div style={{display:"grid",gridTemplateColumns:"repeat(auto-fill,minmax(148px,1fr))",gap:"14px"}}>
          {watched.map(m=><FilmCard key={m.imdbID} m={m} onOpen={onOpen} onTrivia={onTrivia} onRabbit={onRabbit} onRemove={onRemove} onRating={onRating}/>)}
        </div>
      ):(
        <div style={{display:"flex",flexDirection:"column",gap:"8px"}}>
          {watched.map(m=><FilmRow key={m.imdbID} m={m} onOpen={onOpen} onTrivia={onTrivia} onRabbit={onRabbit} onRemove={onRemove} onRating={onRating} onNote={onNote}/>)}
        </div>
      )}
      {watched.length===0&&<Empty n="film" text="No films here yet. Search above to add your first."/>}
    </div>
  );
}

function FilmCard({m,onOpen,onTrivia,onRabbit,onRemove,onRating}){
  const c=MC[m.mood]||"var(--gold)";
  return(
    <div className="hcard" onClick={()=>onOpen(m)} style={{background:"var(--bg2)",border:"1px solid var(--border)",borderRadius:"6px",overflow:"hidden",cursor:"pointer",position:"relative",display:"flex",flexDirection:"column"}}>
      <div style={{height:"3px",background:c,flexShrink:0}}/>
      <div style={{position:"relative"}}>
        <img src={m.Poster&&m.Poster!=="N/A"?m.Poster:"https://via.placeholder.com/148x222/221e16/c8a96e?text=?"} style={{width:"100%",aspectRatio:"2/3",objectFit:"cover",display:"block"}}/>
        <div style={{position:"absolute",bottom:0,left:0,right:0,height:"60px",background:"linear-gradient(to top,rgba(28,24,18,.9),transparent)"}}/>
        {m.userRating>0&&<div style={{position:"absolute",top:"8px",right:"8px",background:"rgba(28,24,18,.8)",borderRadius:"3px",padding:"2px 6px",display:"flex",alignItems:"center",gap:"3px"}}><Icon n="starFill" size={10} color="#c49a38"/><span style={{fontFamily:"var(--sans)",fontSize:"10px",color:"#c49a38"}}>{m.userRating}</span></div>}
      </div>
      <div style={{padding:"10px",flex:1,display:"flex",flexDirection:"column",gap:"4px"}}>
        <div style={{fontFamily:"var(--serif)",fontSize:"13px",lineHeight:"1.3",whiteSpace:"nowrap",overflow:"hidden",textOverflow:"ellipsis"}}>{m.Title}</div>
        <div style={{fontFamily:"var(--sans)",fontSize:"10px",color:"var(--text3)",letterSpacing:"1px"}}>{m.Year}</div>
        <div style={{display:"inline-block",background:c+"16",border:`1px solid ${c}36`,borderRadius:"3px",padding:"1px 7px",fontFamily:"var(--sans)",fontSize:"9px",color:c,letterSpacing:"1.5px",textTransform:"uppercase",marginBottom:"2px"}}>{MOOD_EMOJI[m.mood]} {m.mood}</div>
        <div style={{display:"flex",gap:"5px",marginTop:"2px"}}>
          {[["sparkle","Trivia",onTrivia],["hole","Hole",onRabbit]].map(([icon,label,fn])=>(
            <button key={label} className="hbtn" onClick={e=>{e.stopPropagation();fn(m);}}
              style={{flex:1,background:"var(--bg3)",border:"1px solid var(--border)",color:"var(--text3)",padding:"5px 0",fontSize:"9px",cursor:"pointer",borderRadius:"3px",fontFamily:"var(--sans)",display:"flex",alignItems:"center",justifyContent:"center",gap:"3px"}}>
              <Icon n={icon} size={10} color="var(--text3)"/>{label}
            </button>
          ))}
        </div>
      </div>
    </div>
  );
}

function FilmRow({m,onOpen,onTrivia,onRabbit,onRemove,onRating,onNote}){
  const [editNote,setEditNote]=useState(false);
  const [noteVal,setNoteVal]=useState(m.note||"");
  const c=MC[m.mood]||"var(--gold)";
  return(
    <div style={{background:"var(--bg2)",border:"1px solid var(--border)",borderRadius:"6px",display:"flex",gap:"14px",padding:"12px",borderLeft:`3px solid ${c}`}}>
      <img onClick={()=>onOpen(m)} src={m.Poster&&m.Poster!=="N/A"?m.Poster:"https://via.placeholder.com/44x66/221e16/c8a96e?text=?"} style={{width:"44px",height:"66px",objectFit:"cover",borderRadius:"3px",flexShrink:0,cursor:"pointer",border:"1px solid var(--border)"}}/>
      <div style={{flex:1,minWidth:0}}>
        <div style={{display:"flex",alignItems:"flex-start",justifyContent:"space-between",gap:"8px",marginBottom:"3px"}}>
          <div onClick={()=>onOpen(m)} style={{fontFamily:"var(--display)",fontSize:"16px",cursor:"pointer",whiteSpace:"nowrap",overflow:"hidden",textOverflow:"ellipsis"}}>{m.Title}</div>
          <div style={{display:"flex",gap:"6px",flexShrink:0}}>
            {[["sparkle","trivia",()=>onTrivia(m)],["hole","hole",()=>onRabbit(m)],["trash","remove",()=>onRemove(m)]].map(([icon,lbl,fn])=>(
              <button key={lbl} className="hbtn" onClick={fn} title={lbl} style={{background:"var(--bg3)",border:"1px solid var(--border)",borderRadius:"3px",padding:"4px 6px",cursor:"pointer",display:"flex",alignItems:"center"}}><Icon n={icon} size={12} color="var(--text3)"/></button>
            ))}
          </div>
        </div>
        <div style={{display:"flex",alignItems:"center",gap:"10px",flexWrap:"wrap",marginBottom:"6px"}}>
          <span style={{fontFamily:"var(--sans)",fontSize:"10px",color:"var(--text3)",letterSpacing:"1px"}}>{m.Year}</span>
          {m.imdbRating&&<span style={{fontFamily:"var(--sans)",fontSize:"10px",color:"#c49a38",display:"flex",alignItems:"center",gap:"3px"}}><Icon n="starFill" size={10} color="#c49a38"/>IMDb {m.imdbRating}</span>}
          <span style={{fontFamily:"var(--sans)",fontSize:"9px",color:c,letterSpacing:"1px",background:c+"16",border:`1px solid ${c}30`,borderRadius:"3px",padding:"1px 6px",textTransform:"uppercase"}}>{MOOD_EMOJI[m.mood]} {m.mood}</span>
          <Stars value={m.userRating} onChange={r=>onRating(m.imdbID,r)} size={12}/>
        </div>
        {editNote?(
          <div style={{display:"flex",gap:"6px"}}>
            <input value={noteVal} onChange={e=>setNoteVal(e.target.value)} placeholder="Add a personal note…"
              style={{flex:1,background:"var(--bg3)",border:"1px solid var(--border)",borderRadius:"3px",padding:"5px 10px",color:"var(--text)",fontFamily:"var(--serif)",fontSize:"13px",fontStyle:"italic"}}/>
            <button className="hbtn" onClick={()=>{onNote(m.imdbID,noteVal);setEditNote(false);}} style={{...tB,padding:"5px 10px"}}>Save</button>
          </div>
        ):(
          <div onClick={()=>setEditNote(true)} style={{fontFamily:"var(--serif)",fontSize:"13px",color:m.note?"var(--text2)":"var(--text4)",fontStyle:"italic",cursor:"pointer"}}>
            {m.note||"+ add a note…"}
          </div>
        )}
      </div>
    </div>
  );
}

// ─── WATCHLIST TAB ────────────────────────────────────────────────────────────
function WatchlistTab({watchlist,onMark,onRemove,onOpen}){
  if(!watchlist.length) return <Empty n="bookmark" text="Your watchlist is empty. Search for films above."/>;
  return(
    <div style={{display:"flex",flexDirection:"column",gap:"10px"}}>
      {watchlist.map(m=>(
        <div key={m.imdbID} className="hcard" onClick={()=>onOpen(m)} style={{background:"var(--bg2)",border:"1px solid var(--border)",borderRadius:"6px",display:"flex",gap:"16px",padding:"14px",cursor:"pointer"}}>
          <img src={m.Poster&&m.Poster!=="N/A"?m.Poster:"https://via.placeholder.com/52x78/221e16/c8a96e?text=?"} style={{width:"52px",height:"78px",objectFit:"cover",borderRadius:"3px",flexShrink:0,border:"1px solid var(--border)"}}/>
          <div style={{flex:1}}>
            <div style={{fontFamily:"var(--display)",fontSize:"17px",marginBottom:"4px"}}>{m.Title}</div>
            <div style={{fontFamily:"var(--sans)",fontSize:"10px",color:"var(--text3)",letterSpacing:"1px",marginBottom:"14px"}}>{m.Year} · Added {m.addedDate}</div>
            <div style={{display:"flex",gap:"8px"}}>
              <button className="hbtn" onClick={e=>{e.stopPropagation();onMark(m);}} style={BG}><Icon n="check" size={12} color="var(--bg)"/>Mark Watched</button>
              <button className="hbtn" onClick={e=>{e.stopPropagation();onRemove(m);}} style={{background:"transparent",border:"1px solid var(--border)",color:"var(--text3)",padding:"8px 14px",fontSize:"10px",cursor:"pointer",borderRadius:"4px",fontFamily:"var(--sans)",letterSpacing:"1.5px",display:"flex",alignItems:"center",gap:"6px"}}><Icon n="trash" size={12} color="var(--text3)"/>Remove</button>
            </div>
          </div>
        </div>
      ))}
    </div>
  );
}

// ─── STATS TAB ────────────────────────────────────────────────────────────────
function StatsTab({stats,watched}){
  if(!stats||!watched.length) return <Empty n="chart" text="Watch more films to unlock your stats."/>;
  const hrs=Math.floor(stats.totalRuntime/60),mins=stats.totalRuntime%60;
  const moodDist=MOODS.filter(m=>watched.some(w=>w.mood===m)).map(m=>({m,count:watched.filter(w=>w.mood===m).length})).sort((a,b)=>b.count-a.count);
  const maxMood=Math.max(...moodDist.map(x=>x.count));

  return(
    <div className="fadeIn" style={{display:"grid",gridTemplateColumns:"repeat(auto-fill,minmax(280px,1fr))",gap:"14px"}}>
      {/* Overview */}
      <div style={{background:"var(--bg2)",border:"1px solid var(--border)",borderRadius:"8px",padding:"22px",gridColumn:"span 2"}}>
        <div style={{fontFamily:"var(--sans)",fontSize:"10px",letterSpacing:"3px",color:"var(--text3)",marginBottom:"18px"}}>VAULT OVERVIEW</div>
        <div style={{display:"flex",gap:"32px",flexWrap:"wrap"}}>
          {[
            {label:"Films Watched",value:stats.totalFilms,icon:"film"},
            {label:"Time Spent",value:stats.totalRuntime?`${hrs}h ${mins}m`:"—",icon:"clock"},
            {label:"Avg My Rating",value:stats.avgRating?`${stats.avgRating.toFixed(1)} ★`:"—",icon:"star"},
            {label:"Queued",value:0,icon:"bookmark"},
          ].map(({label,value,icon})=>(
            <div key={label}>
              <div style={{display:"flex",alignItems:"center",gap:"6px",marginBottom:"4px"}}><Icon n={icon} size={13} color="var(--gold)"/><span style={{fontFamily:"var(--sans)",fontSize:"10px",letterSpacing:"2px",color:"var(--text3)"}}>{label.toUpperCase()}</span></div>
              <div style={{fontFamily:"var(--display)",fontSize:"28px",color:"var(--text)"}}>{value}</div>
            </div>
          ))}
        </div>
      </div>

      {/* Mood spectrum */}
      <div style={{background:"var(--bg2)",border:"1px solid var(--border)",borderRadius:"8px",padding:"22px"}}>
        <div style={{fontFamily:"var(--sans)",fontSize:"10px",letterSpacing:"3px",color:"var(--text3)",marginBottom:"18px"}}>EMOTIONAL SPECTRUM</div>
        {moodDist.map(({m,count})=>(
          <div key={m} style={{display:"flex",alignItems:"center",gap:"10px",marginBottom:"10px"}}>
            <div style={{fontFamily:"var(--sans)",fontSize:"10px",color:MC[m],width:"70px",textTransform:"uppercase",letterSpacing:"0.8px"}}>{MOOD_EMOJI[m]} {m}</div>
            <div style={{flex:1,height:"6px",background:"var(--bg4)",borderRadius:"3px",overflow:"hidden"}}>
              <div style={{height:"100%",width:`${(count/maxMood)*100}%`,background:MC[m],borderRadius:"3px",animation:"barFill .8s ease both"}}/>
            </div>
            <div style={{fontFamily:"var(--sans)",fontSize:"11px",color:"var(--text3)",width:"16px",textAlign:"right"}}>{count}</div>
          </div>
        ))}
      </div>

      {/* Top genres */}
      <div style={{background:"var(--bg2)",border:"1px solid var(--border)",borderRadius:"8px",padding:"22px"}}>
        <div style={{fontFamily:"var(--sans)",fontSize:"10px",letterSpacing:"3px",color:"var(--text3)",marginBottom:"18px"}}>TOP GENRES</div>
        {stats.topGenres.map(([g,c],i)=>(
          <div key={g} style={{display:"flex",alignItems:"center",gap:"10px",marginBottom:"10px"}}>
            <div style={{fontFamily:"var(--display)",fontSize:"22px",color:"var(--gold)",opacity:.2,width:"20px",lineHeight:1}}>{i+1}</div>
            <div style={{flex:1}}>
              <div style={{fontFamily:"var(--serif)",fontSize:"14px",marginBottom:"3px"}}>{g}</div>
              <div style={{height:"4px",background:"var(--bg4)",borderRadius:"2px",overflow:"hidden"}}><div style={{height:"100%",width:`${(c/stats.topGenres[0][1])*100}%`,background:"var(--gold)",borderRadius:"2px",animation:"barFill .8s ease both"}}/></div>
            </div>
            <div style={{fontFamily:"var(--sans)",fontSize:"11px",color:"var(--text3)"}}>{c}</div>
          </div>
        ))}
      </div>

      {/* Favourite directors */}
      <div style={{background:"var(--bg2)",border:"1px solid var(--border)",borderRadius:"8px",padding:"22px"}}>
        <div style={{fontFamily:"var(--sans)",fontSize:"10px",letterSpacing:"3px",color:"var(--text3)",marginBottom:"18px"}}>YOUR DIRECTORS</div>
        {stats.topDirectors.map(([d,c],i)=>(
          <div key={d} style={{display:"flex",gap:"12px",alignItems:"center",marginBottom:"14px"}}>
            <div style={{fontFamily:"var(--display)",fontSize:"28px",color:"var(--gold)",opacity:.18,lineHeight:1,width:"22px"}}>{i+1}</div>
            <div>
              <div style={{fontFamily:"var(--serif)",fontSize:"15px"}}>{d}</div>
              <div style={{fontFamily:"var(--sans)",fontSize:"10px",color:"var(--text3)",letterSpacing:"1px"}}>{c} film{c>1?"s":""} in vault</div>
            </div>
          </div>
        ))}
      </div>

      {/* Recent activity */}
      <div style={{background:"var(--bg2)",border:"1px solid var(--border)",borderRadius:"8px",padding:"22px"}}>
        <div style={{fontFamily:"var(--sans)",fontSize:"10px",letterSpacing:"3px",color:"var(--text3)",marginBottom:"18px"}}>RECENTLY WATCHED</div>
        {watched.slice(0,5).map(m=>(
          <div key={m.imdbID} style={{display:"flex",gap:"10px",alignItems:"center",marginBottom:"12px"}}>
            <img src={m.Poster&&m.Poster!=="N/A"?m.Poster:"https://via.placeholder.com/28x42/221e16/c8a96e?text=?"} style={{width:"28px",height:"42px",objectFit:"cover",borderRadius:"2px",border:"1px solid var(--border)"}}/>
            <div>
              <div style={{fontFamily:"var(--serif)",fontSize:"14px"}}>{m.Title}</div>
              <div style={{fontFamily:"var(--sans)",fontSize:"10px",color:"var(--text3)",letterSpacing:"0.5px"}}>{m.watchedDate} · {MOOD_EMOJI[m.mood]} {m.mood}</div>
            </div>
            {m.userRating>0&&<Stars value={m.userRating} size={11}/>}
          </div>
        ))}
      </div>

      {/* Decade breakdown */}
      <div style={{background:"var(--bg2)",border:"1px solid var(--border)",borderRadius:"8px",padding:"22px"}}>
        <div style={{fontFamily:"var(--sans)",fontSize:"10px",letterSpacing:"3px",color:"var(--text3)",marginBottom:"18px"}}>ERA BREAKDOWN</div>
        {Object.entries(watched.reduce((acc,m)=>{const d=Math.floor((parseInt(m.Year)||0)/10)*10;if(d>1900)acc[d]=(acc[d]||0)+1;return acc;},{})).sort((a,b)=>parseInt(a[0])-parseInt(b[0])).map(([dec,c])=>(
          <div key={dec} style={{display:"flex",alignItems:"center",gap:"10px",marginBottom:"8px"}}>
            <div style={{fontFamily:"var(--sans)",fontSize:"10px",color:"var(--text3)",width:"40px",letterSpacing:"1px"}}>{dec}s</div>
            <div style={{flex:1,height:"6px",background:"var(--bg4)",borderRadius:"3px",overflow:"hidden"}}><div style={{height:"100%",width:`${(c/watched.length)*100}%`,background:"var(--teal)",borderRadius:"3px",animation:"barFill .8s ease both"}}/></div>
            <div style={{fontFamily:"var(--sans)",fontSize:"10px",color:"var(--text3)",width:"16px",textAlign:"right"}}>{c}</div>
          </div>
        ))}
      </div>
    </div>
  );
}

// ─── SÉANCE TAB ───────────────────────────────────────────────────────────────
function SeanceTab({seance,onMood,onAdd}){
  const [sel,setSel]=useState(null);
  const STATES=[
    {id:"lost",icon:"eye",label:"Lost & Searching",desc:"When you need cinema to find you"},
    {id:"electric",icon:"sparkle",label:"Electric & Alive",desc:"Buzzing with restless energy"},
    {id:"shattered",icon:"moon",label:"Beautifully Broken",desc:"When sadness feels cinematic"},
    {id:"nostalgic",icon:"film",label:"Drowning in Nostalgia",desc:"Missing something you can't name"},
    {id:"dark",icon:"hole",label:"Embrace the Dark",desc:"Ready to go somewhere uncomfortable"},
    {id:"transcendent",icon:"compass",label:"Seeking Transcendence",desc:"Need a film that expands the universe"},
  ];
  return(
    <div style={{maxWidth:"720px"}}>
      <div style={{textAlign:"center",marginBottom:"34px"}}>
        <div style={{fontFamily:"var(--display)",fontSize:"30px",letterSpacing:"10px",color:"var(--gold)",marginBottom:"10px"}}>THE SÉANCE</div>
        <div style={{fontFamily:"var(--serif)",fontSize:"16px",color:"var(--text3)",fontStyle:"italic"}}>Tell me how you feel. I'll conjure the perfect film from your taste.</div>
      </div>
      {seance.step!=="loading"&&<>
        <div style={{display:"grid",gridTemplateColumns:"repeat(auto-fill,minmax(200px,1fr))",gap:"10px",marginBottom:"18px"}}>
          {STATES.map(s=>(
            <button key={s.id} onClick={()=>setSel(s.id)} style={{background:sel===s.id?"var(--bg4)":"var(--bg2)",border:`1px solid ${sel===s.id?"var(--border2)":"var(--border)"}`,borderRadius:"6px",padding:"18px 16px",cursor:"pointer",textAlign:"left",display:"flex",flexDirection:"column",gap:"8px",transition:"all .18s"}}>
              <Icon n={s.icon} size={18} color={sel===s.id?"var(--gold)":"var(--text3)"}/>
              <div style={{fontFamily:"var(--serif)",fontSize:"15px",color:sel===s.id?"var(--text)":"var(--text2)"}}>{s.label}</div>
              <div style={{fontFamily:"var(--sans)",fontSize:"11px",color:"var(--text3)"}}>{s.desc}</div>
            </button>
          ))}
        </div>
        <button className="hbtn" disabled={!sel} onClick={()=>onMood(sel)} style={{...BG,width:"100%",justifyContent:"center",padding:"13px",fontSize:"11px",letterSpacing:"3px",opacity:sel?1:.38}}>
          <Icon n="sparkle" size={14} color="var(--bg)"/>SUMMON MY FILMS
        </button>
      </>}
      {seance.step==="loading"&&<div style={{display:"flex",flexDirection:"column",alignItems:"center",padding:"80px 0",gap:"22px"}}>
        <div style={{width:"62px",height:"62px",borderRadius:"50%",border:"1px solid var(--border2)",animation:"orb 2s ease-in-out infinite",background:"radial-gradient(circle,rgba(200,169,110,.07),transparent)"}}/>
        <div style={{fontFamily:"var(--sans)",fontSize:"11px",letterSpacing:"3px",color:"var(--text3)"}}>READING YOUR CINEMATIC SOUL</div>
      </div>}
      {seance.step==="results"&&seance.recs.length>0&&<div className="fadeIn" style={{marginTop:"28px"}}>
        <div style={{fontFamily:"var(--sans)",fontSize:"10px",letterSpacing:"3px",color:"var(--text3)",marginBottom:"16px"}}>CONJURED FOR YOUR STATE OF MIND</div>
        <div style={{display:"flex",flexDirection:"column",gap:"11px"}}>
          {seance.recs.map((r,i)=>(
            <div key={i} style={{background:"var(--bg2)",border:"1px solid var(--border)",borderRadius:"6px",padding:"18px",display:"flex",gap:"14px",alignItems:"flex-start"}}>
              <div style={{fontFamily:"var(--display)",fontSize:"26px",color:"var(--gold)",opacity:.18,lineHeight:1,flexShrink:0,width:"24px"}}>{i+1}</div>
              <div style={{flex:1}}>
                <div style={{fontFamily:"var(--display)",fontSize:"18px",marginBottom:"5px"}}>{r.title} <span style={{color:"var(--text3)",fontSize:"14px",fontStyle:"normal"}}>({r.year})</span></div>
                <div style={{fontFamily:"var(--serif)",fontSize:"15px",color:"var(--text2)",fontStyle:"italic",lineHeight:"1.65",marginBottom:"7px"}}>{r.why}</div>
                {r.obscurityScore>7&&<div style={{display:"flex",alignItems:"center",gap:"5px",fontFamily:"var(--sans)",fontSize:"10px",color:"var(--teal)",letterSpacing:"1.5px"}}><Icon n="eye" size={11} color="var(--teal)"/>RARE FIND · {r.obscurityScore}/10</div>}
              </div>
              <button className="hbtn" onClick={()=>onAdd({Title:r.title,Year:r.year,imdbID:`tt_s${i}`,Poster:"N/A"})} style={{background:"transparent",border:"1px solid var(--border2)",borderRadius:"50%",width:"33px",height:"33px",display:"flex",alignItems:"center",justifyContent:"center",cursor:"pointer",flexShrink:0}}>
                <Icon n="bookmark" size={14} color="var(--gold)"/>
              </button>
            </div>
          ))}
        </div>
      </div>}
    </div>
  );
}

// ─── DNA TAB ──────────────────────────────────────────────────────────────────
function DNATab({dna,loading,onRegen}){
  if(loading) return <div style={{display:"flex",flexDirection:"column",alignItems:"center",padding:"100px 0",gap:"22px"}}><div style={{width:"78px",height:"78px",borderRadius:"50%",border:"2px solid var(--border2)",animation:"orb 1.8s ease-in-out infinite",boxShadow:"0 0 40px rgba(200,169,110,.08)"}}/><div style={{fontFamily:"var(--sans)",fontSize:"11px",letterSpacing:"3px",color:"var(--text3)"}}>SEQUENCING YOUR CINEMATIC GENOME</div></div>;
  if(!dna) return <div style={{display:"flex",justifyContent:"center",paddingTop:"80px"}}><button className="hbtn" onClick={onRegen} style={BG}><Icon n="dna" size={14} color="var(--bg)"/>Analyze My Cinema DNA</button></div>;
  return(
    <div className="fadeIn" style={{maxWidth:"640px"}}>
      <div style={{fontFamily:"var(--display)",fontSize:"34px",fontStyle:"italic",color:"var(--gold)",marginBottom:"12px"}}>{dna.archetype}</div>
      <div style={{fontFamily:"var(--serif)",fontSize:"16px",color:"var(--text2)",lineHeight:"1.78",fontStyle:"italic",borderLeft:"3px solid var(--border2)",paddingLeft:"18px",marginBottom:"32px"}}>{dna.verdict}</div>
      <div style={{fontFamily:"var(--sans)",fontSize:"10px",letterSpacing:"3px",color:"var(--text3)",marginBottom:"18px"}}>YOUR CINEMATIC GENOME</div>
      {dna.dnaStrands?.map((s,i)=>(
        <div key={i} style={{display:"flex",alignItems:"center",gap:"14px",marginBottom:"14px"}}>
          <div style={{fontFamily:"var(--sans)",fontSize:"10px",letterSpacing:"2px",color:"var(--text3)",width:"84px",flexShrink:0,textTransform:"uppercase"}}>{s.label}</div>
          <div style={{flex:1,height:"5px",background:"var(--bg4)",borderRadius:"3px",overflow:"hidden"}}><div style={{height:"100%",width:`${s.score}%`,background:s.color||"var(--gold)",borderRadius:"3px",animation:`barFill .9s ease both`,animationDelay:`${i*.1}s`}}/></div>
          <div style={{fontFamily:"var(--sans)",fontSize:"11px",color:"var(--gold)",width:"26px",textAlign:"right"}}>{s.score}</div>
        </div>
      ))}
      <div style={{display:"grid",gridTemplateColumns:"1fr 1fr",gap:"11px",marginTop:"26px",marginBottom:"22px"}}>
        {[{label:"Director Soul",value:dna.directorSoul},{label:"Cinematic Era",value:dna.era},{label:"Your Blind Spot",value:dna.blindspot,span:2,warn:true}].map((c,i)=>(
          <div key={i} style={{background:"var(--bg2)",border:`1px solid ${c.warn?"rgba(184,80,64,.3)":"var(--border)"}`,borderRadius:"6px",padding:"16px",gridColumn:c.span?`span ${c.span}`:undefined}}>
            <div style={{fontFamily:"var(--sans)",fontSize:"10px",letterSpacing:"2.5px",color:c.warn?"var(--red)":"var(--text3)",marginBottom:"7px"}}>{c.label.toUpperCase()}</div>
            <div style={{fontFamily:"var(--serif)",fontSize:"16px",fontStyle:"italic"}}>{c.value}</div>
          </div>
        ))}
      </div>
      <button className="hbtn" onClick={onRegen} style={BO}><Icon n="refresh" size={13} color="var(--gold)"/>Re-analyze</button>
    </div>
  );
}

// ─── DISCOVER TAB ─────────────────────────────────────────────────────────────
function DiscoverTab({recs,loading,onAdd,onOpen,onRefresh}){
  if(loading) return <div style={{display:"flex",flexDirection:"column",alignItems:"center",padding:"100px 0",gap:"22px"}}><div style={{width:"58px",height:"58px",borderRadius:"50%",border:"1px solid rgba(94,158,150,.5)",animation:"orbTeal 1.8s ease-in-out infinite",background:"radial-gradient(circle,rgba(94,158,150,.06),transparent)"}}/><div style={{fontFamily:"var(--sans)",fontSize:"11px",letterSpacing:"3px",color:"var(--text3)"}}>SCANNING THE ARCHIVE FOR YOU</div></div>;
  return(
    <div>
      <div style={{display:"flex",justifyContent:"space-between",alignItems:"flex-end",marginBottom:"24px"}}>
        <div>
          <div style={{fontFamily:"var(--display)",fontSize:"26px",letterSpacing:"6px",color:"var(--gold)",marginBottom:"4px"}}>THE VAULT</div>
          <div style={{fontFamily:"var(--serif)",fontSize:"14px",color:"var(--text3)",fontStyle:"italic"}}>Hidden gems, curated from your taste profile via Claude</div>
        </div>
        <button className="hbtn" onClick={onRefresh} style={BO}><Icon n="refresh" size={13} color="var(--gold)"/>New Gems</button>
      </div>
      <div style={{display:"flex",flexDirection:"column",gap:"11px"}}>
        {recs.map((r,i)=>(
          <div key={i} className="hcard" style={{background:"var(--bg2)",border:"1px solid var(--border)",borderLeft:"3px solid var(--teal)",borderRadius:"6px",padding:"20px",display:"flex",gap:"16px"}}>
            <div style={{fontFamily:"var(--display)",fontSize:"30px",color:"var(--teal)",opacity:.2,lineHeight:1,flexShrink:0,width:"34px"}}>{String(i+1).padStart(2,"0")}</div>
            <div style={{flex:1}}>
              <div style={{fontFamily:"var(--display)",fontSize:"19px",marginBottom:"3px"}}>{r.title} <span style={{color:"var(--text3)",fontSize:"14px",fontStyle:"normal"}}>({r.year})</span></div>
              <div style={{fontFamily:"var(--serif)",fontSize:"13px",color:"var(--gold)",fontStyle:"italic",marginBottom:"8px"}}>dir. {r.director}</div>
              <div style={{fontFamily:"var(--serif)",fontSize:"15px",color:"var(--text2)",fontStyle:"italic",lineHeight:"1.65",marginBottom:"8px"}}>{r.pitch}</div>
              <div style={{display:"flex",alignItems:"center",gap:"10px"}}>
                {r.vibe&&<span style={{fontFamily:"var(--sans)",fontSize:"10px",color:"var(--teal)",letterSpacing:"2px"}}>{r.vibe.toUpperCase()}</span>}
                {r.obscurityScore&&<span style={{fontFamily:"var(--sans)",fontSize:"10px",color:"var(--text3)",letterSpacing:"1px"}}>· obscurity {r.obscurityScore}/10</span>}
              </div>
            </div>
            <button className="hbtn" onClick={()=>onAdd({Title:r.title,Year:r.year,imdbID:`tt_d${i}`,Poster:"N/A"})} style={{background:"transparent",border:"1px solid rgba(94,158,150,.4)",borderRadius:"50%",width:"36px",height:"36px",display:"flex",alignItems:"center",justifyContent:"center",cursor:"pointer",flexShrink:0,alignSelf:"center"}}>
              <Icon n="bookmark" size={15} color="var(--teal)"/>
            </button>
          </div>
        ))}
      </div>
      {!recs.length&&<Empty n="compass" text="Add more films to your vault to unlock recommendations."/>}
    </div>
  );
}
