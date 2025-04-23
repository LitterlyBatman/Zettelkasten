In order to write readable, functional and easily debuggable code, there are rules programmers follow to make coding and reproducing it allot easier.

```
func main () {
	if !isMaintenancePeriod {
		if isAutenticatedUser {
			if AuthorizedUser {
				for _, product := range cart {
					switch product.Type() {
					case 'alcohol':
						total += alcoholTax
					case 'electronics':
						total += electronicsTax
					default:
						total += generalTax
					}
				} else {
					log.Fatalf("user not authorised")
				}
			
			} else {
				log.Fatal("invalid user credentials")
			}
		} else {
			log.Fatalf("feauture unavailable)
		}
	}
}

```

## 1 Avoid deeply nested code

Deeply nested code:
> deep nesting reffers to code that has many indentation levels due to the use of many structures like "functoins, loops, statements" this generally makes your code harder to read, more difficult to debug or maintain,  but most of all prone to making mistakes.

one way of avoiding this is using invertion on your methods, this means inverting the conditionals, so handling edge cases or invalid conditions early.

for example, by changing the main function, like this
```
if !isMaintenancePeriod {
	log.Fatalf("feauture unavailable)
} 
// core comditions
