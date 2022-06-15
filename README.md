# Svelte Css MediaQuery 🐥

### [Demo - Svelte REPL](https://svelte.dev/repl/ffdcf39ff71f4d549961c45880645294?version=3.48.0)
### Lightweight, comfortable, like Svelte🐣

## how to install
```npm
npm i svelte-css-mediaquery
```
## how to use

### Query? Yes, just like in CSS🙊
```js
query='(min-width: 768px) and (max-width: 1280px)'
```
### Matches? This is your result
#### Component (`bind:` directive)
```
bind:matches
------------------
bind:matches={foo}
```
#### Slot (`let:` directive)
```
let:matches
------------------
let:matches={foo}
```
### Examples
#### Slot
```svelte
<MediaQuery query='(max-width: 480px)' let:matches>
  {#if matches}
    mobile!!
  {/if}
</MediaQuery>
```
#### Bind
```svelte
<script>
  let matches
</script>

<MediaQuery query='(max-width: 480px)' bind:matches/>

{#if matches}
  mobile!!
{/if}

{#if matches}
  Oh my God, it's really mobile
{/if}
```

### That's not all!
#### You can use an array from `query`
```js
query={['(max-width: 1200px)', '(min-width: 800px)']}
```
What about matches?  
Matches will take everything from `query` in order  
```js
matches=[boolean, boolean]
```
#### You can test this in [Svelte REPL](https://svelte.dev/repl/ffdcf39ff71f4d549961c45880645294?version=3.48.0)🐥
#### Example
```svelte
<MediaQuery query={['(max-width: 768px)', '(min-width: 768px) and (max-width: 1280px)', '(min-width: 1280px)']} let:matches>
	{@const [mobile, tablet, desktop] = matches}
	<h5>
		mobile: '(max-width: 768px)' = {mobile}
		tablet: '(max-width: 1280px)' = {tablet}
		desktop: '(min-width: 1280px)' = {desktop}
	</h5>
</MediaQuery>
```
`{@const}` - [Svelte Docs](https://svelte.dev/docs#template-syntax-const)🐹  
You can also use it through the array index `tablet = matches[1]`  
With `bind:`, everything is the same🐥  
