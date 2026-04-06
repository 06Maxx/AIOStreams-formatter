# AIOSteams template by 06Maxx

### AIOSteams movie/show selection

<img width="524" height="170" alt="stremio-shell-ng 2026-06-04 212230" src="https://github.com/user-attachments/assets/0345c24e-cbcd-46f0-abe0-cbb2ec31bd2a" />

### 1. Name template
```
{service.shortName::exists["[{service.shortName}"||""]}{service.cached::istrue["⚡]"||""]}{service.cached::isfalse["☁️]"||""]} {addon.name} {stream.resolution::replace('2160p','4K⠀⠀⠀')::replace('1440p','2K⠀⠀⠀')::replace('1080p','1080p⠀⠀⠀')::replace('720p','720p⠀⠀⠀')}
```

### 2. Description template
```
🎬 {stream.seasonEpisode::exists["{stream.seasonEpisode::join(' · ')} · "||""]}{stream.filename::~complete["(Complete) "||""]}{stream.filename::~extended["(Extended) "||""]}{stream.title}{stream.year::exists[" ({stream.year})"||""]}
🎞️ {stream.filename::~remux["BR REMUX"||"{stream.quality}"]} 🏷️ {stream.visualTags::exists["{stream.visualTags}"||"{stream.encode}"]}
📦 {stream.size::bytes} 📡 {stream.indexer::exists["{stream.indexer}"||"RD"]}
🔊 {stream.audioChannels::exists["{stream.audioChannels::join(' · ')} "||""]}{stream.audioTags::exists["{stream.audioTags::join(' · ')}"||"Unknown"]}
🌍 {stream.languages::exists["{stream.smallLanguageCodes::join(' · ')::replace('ᴅᴜᴀʟ ᴀᴜᴅɪᴏ','ᴅᴜᴏ')::replace('ᴅᴜʙʙᴇᴅ','ᴅᴜʙ')}"||"ᴏʀɪɢɪɴᴀʟ"]}
```
