Stop clicking "View impressions" accidentally on twitter. Put the Like button where it belongs.
## Before
<img width="440" alt="image" src="https://user-images.githubusercontent.com/23417273/213728686-875c2173-6902-48cb-982f-e88b990aa95d.png">

## After
<img width="440" alt="image" src="https://user-images.githubusercontent.com/23417273/213728496-0e9cb202-e02b-421a-8594-e2daca7521fa.png">

# Install
- Install a userscript manager such as [Tampermonkey](https://www.tampermonkey.net/)
- [Click here](https://raw.githubusercontent.com/arshxyz/twitterswitchback/main/twtscript.user.js) to install the script
# Alternatively
Paste the following code into your console to use the script without Tampermonkey. Does not persist through reloads.
```js
function update(e){function t(e,t){const r=document.createComment("");t.replaceWith(r),e.replaceWith(t),r.replaceWith(e)}let r=e.querySelectorAll("article[data-testid='tweet']");0!=r.length&&r.forEach((e=>{let r=e.querySelector("div[role='group']").childNodes;1!=r.length&&(r[3].querySelectorAll("div[data-testid='like']").length>0||r[3].querySelectorAll("div[data-testid='unlike']").length>0||(t(r[2],r[3]),t(r[1],r[2]),t(r[0],r[1])))}))}async function main(){new MutationObserver(((e,t)=>{try{for(const t of e){"attributes"===t.type&&update(t.target);for(const e of t.addedNodes)update(e)}}catch(e){}})).observe(document,{childList:!0,subtree:!0,attributes:!0}),update(document)}main();
```
