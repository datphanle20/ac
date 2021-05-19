# ac
Help me!!
package main

import (
	"fmt"
	// "html"
	"log"
	"net/http"
)

func main() {

	http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
		r.ParseForm()
		fmt.Println(r.PostForm)
		http.Redirect(w,r,"https://assessment-dat.webflow.io/comfirmation?total=%sum&message=ok",http.StatusSeeOther)
	})

	log.Fatal(http.ListenAndServe(":8081", nil))

}
