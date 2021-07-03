# vite-ssr-next-auth
Sample repo to make next-auth work with vite-plugin-ssr

[Next-Auth](https://next-auth.js.org) is an extremly simple authentication library that was developed for Nextjs framework. 

This repo shows how to next-auth with vite-plugin-ssr.
As a matter of fact, you can use the same pattern to add authentication to any node based framework with little bit of tweaking. 

    app.get("/api/auth/*", (req, res) => {
    
    const nextauth = req.path.split("/");
    
    nextauth.splice(0, 3);
    
    req.query.nextauth = nextauth; // next-auth expects this
    
    NextAuthHandler(req, res)
    
    });
    
    app.post("/api/auth/*", (req, res) => {
    
    const nextauth = req.path.split("/");
    
    nextauth.splice(0, 3);
    
    req.query.nextauth = nextauth; // next-auth expects this
    
    NextAuthHandler(req, res)
    
    });

You can refer to a full-blown starter here: https://github.com/s-kris/vite-ssr-starter
