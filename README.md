# Facebook-Cleaner
Clean All Your Facebook Information

Paste the Following Code to the Javscript Console So That to Kick Everything in Your Facebook.

```
  function clean()
  {
  var buttons = document.querySelectorAll('[aria-label="Allowed on Timeline"]');
  if(buttons.length==0)
  {
      console.log("Empty");
      window.scrollBy(0, 3000);
      setTimeout(function(){clean();}, 1000);
  }
  else
  {
    console.log("Handling");
    var button = buttons[0];
    setTimeout(function() 
    { 
        button.scrollIntoView( true );
        window.scrollBy(0, -200);
        button.focus();
        setTimeout(function() 
        { 
            button.click();
            setTimeout(function() 
                { 
                  owns = button.getAttribute('aria-owns');
                  console.log("class:"+owns);
                  link = document.querySelectorAll('#'+owns+' [ajaxify^="/ajax/timeline/all_activity/visibility.php?action=hide"]');
                  link1 = document.querySelectorAll('#'+owns+' [ajaxify^="/ajax/timeline/delete/confirm"]');
                  link2 = document.querySelectorAll('#'+owns+' [ajaxify^="/ajax/timeline/all_activity/remove_content.php"]');
                  
                  if(link[0]){
                    link[0].click();
                    console.log("Click Link Hide");
                  }

                  else if(link1[0]){
                    link1[0].click();
                    
                    
                    console.log("Ready to click delete");
                    setTimeout(function() { 
                          form = document.querySelectorAll('[action^="/ajax/timeline/delete"] button');
                          form[0].click();
                          setTimeout(function(){clean();}, 6000);
                          //window.scrollBy(0, 2000);
                          //window.scrollBy(0, -2000);

                    },2000);
                  }
                  else if(link2[0]){
                    link2[0].click();
                    //alert(link2[0]);
                    console.log("Click Link Unlike");
                  }

                  if (link1[0])
                  {

                  }
                  else
                  {                  
                  setTimeout(function(){clean();}, 3000);
                  //window.scrollBy(0, 2000);
                  //window.scrollBy(0, -2000);
                }

              }, 200);
        }, 200);
    }, 250);
  }
}
  
```

