# Ruby on Rails

While I largely believe RoR is a pile of flaming fire "organizationally" it does have some strong consistency which I really enjoy. That said there's a lot to build on top of when building a Dru style application.

{% embed url="https://medium.com/@dan\_manges/the-modular-monolith-rails-architecture-fb1023826fc4" %}

```text
~/
   .. normal rails app stuff ..
   gems/
   engines/ 
```

Adding a new "DLL" \(stateless logic\) is simply `bundle gem abc`

* could include ActiveSupport code

 Adding a new engine \(Models, Views, Controllers\)

[https://guides.rubyonrails.org/engines.html](https://guides.rubyonrails.org/engines.html) 

`rails plugin new <engine name> --mountable`

