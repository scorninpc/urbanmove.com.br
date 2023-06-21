base de conhecimento e documentação futura

# Documentação

## CSS

### filho mais proximo

O simbolo `>` pega o filho mais proximo. Por exemplo:

```html
<div>
	<span>
		<ul>
			<li></li>
		</ul>
	</span>
	<ul>
		<li>
			<a></a>
		</li>
		<li>
			<a></a>
		</li>
		<li>
			<a></a>
		</li>
		<li>
			<a></a>
		</li>
	</ul>
</div>
```

O seletor `div ul` vai retornar as 2 `UL`.
O seletor `div > ul` só vai pegar o `UL` que é filho direto da `DIV`. 
O seletor `div > span > ul` vai pegar o `UL` de dentro do `SPAN`, porque o `UL` é filho direto do `SPAN`, que é filho direto do `DIV`
