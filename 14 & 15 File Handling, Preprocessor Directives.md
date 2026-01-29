## 14: File Handling

### File Operations

* Create/Open → `fopen()`
* Read → `fscanf()`, `fgets()`
* Write → `fprintf()`, `fputs()`
* Close → `fclose()`

```c
FILE *fp = fopen("data.txt", "w");
fprintf(fp, "Hello File");
fclose(fp);
```

---

## 15: Preprocessor Directives

### Common Directives

* `#include`
* `#define`
* `#undef`
* `#ifdef`, `#ifndef`

```c
#define PI 3.14
```

---
