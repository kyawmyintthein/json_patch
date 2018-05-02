Merge json to existing struct

Example

```

package main

import "errors"
import "github.com/kyawmyintthein/json_patch"

type User struct{
  Name string `json:"name"`
  Email string `json:"email"`
}

func main(){
  user := User{Name: "Richard"}
  src := []byte(`{"name": "John"}`)
 
  err := jsonpath.PatchValues(src, &user)
  if err != nil{
    fmt.Println(err)
  }
 
}
```


