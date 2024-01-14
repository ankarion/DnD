
```dataview
table without id
sum(number(filter(flat(rows.rewards), (t)=>contains(t, "оп")))) as оп,
sum(number(filter(flat(rows.rewards), (t)=>contains(t, "зм")))) as зм,
sum(number(filter(flat(rows.rewards), (t)=>contains(t, "сухпай")))) as сухпай
from "CompaignTwo"
where rewards and this.file.folder=file.folder
group by true
```
[[leveling.js|manual]]
