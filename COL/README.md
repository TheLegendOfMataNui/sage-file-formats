# SAGE File Format: COL

Archive format similar to a BLK file but with multiple compression algorithms.

Entries can have either string names or names hashed with `SrHashString` (a BKDR hash).

```c++
// BKDR hash
unsigned int __cdecl SrHashString(const _ScBaseString *str) {
	char * cstr = str->cstr;
	unsigned int result = 0;
	while (*cstr) {
		result = *cstr++ + 131 * result;
	}
	return result;
}
```
