# object join

```javascript
const join =  (obj, glue = '=', separator = '&') => {
	return Object.getOwnPropertyNames(obj).map((key) => {
		return [key, obj[key]].join(glue)
	}).join(separator)
}

var obj = {
	name: 'ClaudeSeo',
	age: 21
}
console.log(join(obj))

>> name=ClaudeSeo&age=21
```
