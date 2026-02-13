# AIOSteams custom formatter

### Table of contents

* [AIOStreams](#-aiosteams)

* [🦅 AIOSteams configs](#-aiosteams-configs)
    * [1. Formatter name](#1-formatter-name)
    * [2. Formatter description](#2-formatter-description)
   
### AIOSteams
```
{
AIOMetadata: https://aiometadatafortheweebs.midnightignite.me/
AIOStreams: https://aiostreamsfortheweebs.midnightignite.me/
Comet: https://cometfortheweebs.midnightignite.me/
Mediafusion: https://mediafusionfortheweebs.midnightignite.me/
Stremthru: https://stremthrufortheweebs.midnightignite.me/
Kitsu: https://kitsufortheweebs.midnightignite.me/
EasyNews++: https://easynewsppfortheweebs.midnightignite.me/
Jackettio: https://jackettiofortheweebs.midnightignite.me/configure
https://aiolistsfortheweebs.midnightignite.me/
}
```

### 1. Formatter name
```
{
{service.shortName::exists["[{service.shortName}"||""]}{service.cached::istrue["⚡]"||""]}{service.cached::isfalse["☁️]"||""]} {addon.name} {stream.resolution::replace('2160p','4K⠀⠀⠀')::replace('1440p','2K⠀⠀⠀')::replace('1080p','1080p⠀⠀⠀')::replace('720p','720p⠀⠀⠀')}
}
```

### 2. Formatter description
```
{
🎬 {stream.seasonEpisode::exists["{stream.seasonEpisode::join(' · ')} · "||""]}{stream.filename::~complete["(Complete) "||""]}{stream.filename::~extended["(Extended) "||""]}{stream.title}{stream.year::exists[" ({stream.year})"||""]}
🎞️ {stream.filename::~remux["BR REMUX"||"{stream.quality}"]} 🏷️ {stream.visualTags::exists["{stream.visualTags}"||"{stream.encode}"]}
📦 {stream.size::bytes} 📡 {stream.indexer::exists["{stream.indexer}"||"RD"]}
🔊 {stream.audioChannels::exists["{stream.audioChannels::join(' · ')} "||""]}{stream.audioTags::exists["{stream.audioTags::join(' · ')}"||"Unknown"]}
🌍 {stream.languages::exists["{stream.smallLanguageCodes::join(' · ')::replace('ᴅᴜᴀʟ ᴀᴜᴅɪᴏ','ᴅᴜᴏ')::replace('ᴅᴜʙʙᴇᴅ','ᴅᴜʙ')}"||"ᴏʀɪɢɪɴᴀʟ"]}
}
```
