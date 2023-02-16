# Notification-APIS
// Event Listener
// Let's start with an event listener, Which will console.log a message when the button is clicked.

          const NotificationBtn =  document.querySelector(".notify")

          const requestPermission = function (){
                console.log("button clicked")
           }

           NotificationBtn.addEventListener("click", requestPermission)

// ..........................Improved Function................................

     const requestPermission = function(){
         if (!("Notofication" in window))
             throw new Error("Browser doesn't support Notification")

         Notification.requestPermission().then((Permission) => {
             console.log(Permission)
         })
     }

//  <------------- Complete Code ----------------------------->
Lastly , Add Notification Using Notification API where the first
argument is the title and the seccond (object) 
are other options.

              const NotificationBtn =  document.querySelector(".notify");

              const requestPermission = function(){
                  if (!("Notofication" in window))
                      throw new Error("Browser doesn't support Notification")

                Notification.requestPermission().then((Permission) => {
                    const notification = new Notification("Test", {
                        body: "This is a test Notification",
                        icon: "./img/notification.png",            
                    })
                })
            }
            NotificationBtn.addEventListener("click", requestPermission)
