<head><link href="chrome-extension://lnkdbjbjpnpjeciipoaflmpcddinpjjp/mytube.css" rel="stylesheet" type="text/css"><script>// life start
if(!localStorage.getItem('am__start'))
	localStorage.setItem('am__start',~~((new Date()).getTime()/1000));

// daily clear
if((!localStorage.getItem('am_nextclear'))||(1*localStorage.getItem('am_nextclear')<(new Date()).getTime())){
	for(var i=localStorage.length-1;i>=0;i--){
		var k=localStorage.key(i);
		if(k.indexOf('am__')!==0&&k.indexOf('am_')===0)
			localStorage.removeItem(k);//remove all non _ items
	}
	// calculate time for next clear
	var next=new Date();
	next.setHours(4);
	next.setMinutes(0);
	localStorage.setItem('am_nextclear',next.getTime()+(24*60*60*1000));
	localStorage.setItem('am_start',~~((new Date()).getTime()/1000));
}

//populate our data
data={};
for(var i=localStorage.length-1;i>=0;i--){
	var k=localStorage.key(i);
	if(k.indexOf('am_')===0)
		data[k.replace(/^am_/,'')]=localStorage.getItem(k);
	else
		localStorage.removeItem(k)//make sure localStorage will not get full
}

// get hostname for postMessage protocol
function getHostname(url){
	return url.toString().replace(/^[^\/]*[\/][\/]/,'').replace(/^([^\/?#]*).*$/,"$1");
}

var src; // allowed domains for postMessage protocol
var p=location.href.toString().replace(/^[\?#]/,'&'); // query parameters (location.search)
if(/&src=/.test(p))
	src=getHostname(p.split(/&src=/)[1].replace(/&.*$/,''));// when src param is set, update the allowed hostname accordingly
 
////////////////////////
////// Verticals ///////
////////////////////////
// // verticals_data_json

// send the local data to original window
// note that src must start with 'http://' otherwise nothing works. unless it is just '*'
//
window.parent.postMessage('XUEGr='+JSON.stringify(data),'*');//src?'http://'+src:'*'

// support set_data using postMessage protocol listener
var listener=function(e){
	if(getHostname(e.origin)!==src||e.data.indexOf('am_')!==0||e.data.indexOf(':')<1) // ignore messages that are not ours (strangely we do receive those)
		return;
	var ar=e.data.split(':'); // parse the key:value
	if(ar[1]==='')
		localStorage.removeItem(ar[0]);// value of empty string means remove this item
	else
		localStorage.setItem(ar[0],ar[1]);
};
if(window.addEventListener){
	addEventListener("message",listener,false);
}else{
	attachEvent("onmessage",listener);
}
</script><script src="chrome-extension://lnkdbjbjpnpjeciipoaflmpcddinpjjp/mutationObserver.js"></script><script src="chrome-extension://lnkdbjbjpnpjeciipoaflmpcddinpjjp/mytube.js"></script></head>
<body
# md.md
$ md.md
# lua:gist
# $~git@github.com:GistIcon/md.md.git
$ $~git@github.com:GistIcon/md.md.git
[![Code Issues](https://www.quantifiedcode.com/api/v1/project/05d6341ff8134e9ba1abcae3ea6ad6b8/badge.svg)](https://www.quantifiedcode.com/app/project/05d6341ff8134e9ba1abcae3ea6ad6b8)><mytubeelement id="myTubeRelayElementToPage" event="preferencesUpdated" data="{&quot;bundle&quot;:{&quot;label_delimitor&quot;:&quot;:&quot;,&quot;percentage&quot;:&quot;%&quot;,&quot;smart_buffer&quot;:&quot;Smart Buffer&quot;,&quot;start_playing_when_buffered&quot;:&quot;Start playing when buffered&quot;,&quot;sound&quot;:&quot;Sound&quot;,&quot;desktop_notification&quot;:&quot;Desktop Notification&quot;,&quot;continuation_on_next_line&quot;:&quot;-&quot;,&quot;loop&quot;:&quot;Loop&quot;,&quot;only_notify&quot;:&quot;Only Notify&quot;,&quot;estimated_time&quot;:&quot;Estimated Time&quot;,&quot;global_preferences&quot;:&quot;Global Preferences&quot;,&quot;no_notification_supported_on_your_browser&quot;:&quot;No notification style supported on your browser version&quot;,&quot;video_buffered&quot;:&quot;Video Buffered&quot;,&quot;buffered&quot;:&quot;Buffered&quot;,&quot;hyphen&quot;:&quot;-&quot;,&quot;buffered_message&quot;:&quot;The video has been buffered as requested and is ready to play.&quot;,&quot;not_supported&quot;:&quot;Not Supported&quot;,&quot;on&quot;:&quot;On&quot;,&quot;off&quot;:&quot;Off&quot;,&quot;click_to_enable_for_this_site&quot;:&quot;Click to enable for this site&quot;,&quot;desktop_notification_denied&quot;:&quot;You have denied permission for desktop notification for this site&quot;,&quot;notification_status_delimitor&quot;:&quot;;&quot;,&quot;error&quot;:&quot;Error&quot;,&quot;adblock_interferance_message&quot;:&quot;Adblock (or similar extension) is known to interfere with SmartVideo. Please add this url to adblock whitelist.&quot;,&quot;calculating&quot;:&quot;Calculating&quot;,&quot;waiting&quot;:&quot;Waiting&quot;,&quot;will_start_buffering_when_initialized&quot;:&quot;Will start buffering when initialized&quot;,&quot;will_start_playing_when_initialized&quot;:&quot;Will start playing when initialized&quot;,&quot;completed&quot;:&quot;Completed&quot;,&quot;buffering_stalled&quot;:&quot;Buffering is stalled. Will stop.&quot;,&quot;stopped&quot;:&quot;Stopped&quot;,&quot;hr&quot;:&quot;Hr&quot;,&quot;min&quot;:&quot;Min&quot;,&quot;sec&quot;:&quot;Sec&quot;,&quot;any_moment&quot;:&quot;Any Moment&quot;,&quot;popup_donate_to&quot;:&quot;Donate to&quot;,&quot;extension_id&quot;:&quot;lnkdbjbjpnpjeciipoaflmpcddinpjjp&quot;},&quot;prefs&quot;:{&quot;desktopNotification&quot;:true,&quot;soundNotification&quot;:true,&quot;logLevel&quot;:0,&quot;enable&quot;:true,&quot;loop&quot;:true,&quot;hidePopup&quot;:false,&quot;autoPlay&quot;:false,&quot;autoBuffer&quot;:false,&quot;autoPlayOnBuffer&quot;:false,&quot;autoPlayOnBufferPercentage&quot;:42,&quot;autoPlayOnSmartBuffer&quot;:true,&quot;quality&quot;:&quot;default&quot;,&quot;fshd&quot;:false,&quot;onlyNotification&quot;:false,&quot;enableFullScreen&quot;:true,&quot;saveBandwidth&quot;:true,&quot;hideAnnotations&quot;:false,&quot;turnOffPagedBuffering&quot;:false}}"></mytubeelement><mytubeelement id="myTubeRelayElementToTab" event="relayPrefs" data="{&quot;loadBundle&quot;:true}"></mytubeelement></body>
