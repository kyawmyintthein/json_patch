

# JSONPATCH

**Description**
 > Merging json to existing struct. Support for nested struct, Slice, Interface, primitive type except Ptr and Complex number and Map.         


**Example**
```
package main  
  
import (  
   "fmt"  
   "github.com/kyawmyintthein/jsonpatch"
 )  
  
type User struct {  
   Name  string `json:"name"`  
  Email string `json:"email"`  
}  
  
func main() {  
   user := User{Name: "Richard", Email: "contact@richard.com"}  
   src := []byte(`{"name": "John", "email": "contact@john.com"}`)  
   fmt.Printf("Before Patch : %+v \n", user)  
   
   err := jsonpatch.PatchValues(src, &user)  
   if err != nil {  
      fmt.Println(err)  
   }  
   fmt.Printf("After Patch : %+v \n", user)  
}
```

**Result**

> Before Patch : {Name:Richard Email:contact@richard.com} 

> After Patch : {Name:John Email:contact@john.com}


