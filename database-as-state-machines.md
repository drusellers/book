# Databases as State Machines

Talk by Heroku DoD



https://engineering.shopify.com/17488160-why-developers-should-be-force-fed-state-machineshttps://content.pivotal.io/blog/maintainable-state-machines-part-2-don-t-store-state-names-in-the-database

## Feel

up? - thing.checkUp

rows - thing.countRows



## State

```ruby
state :available do
    unless up?
        transition :offline
    end
    
    if rows > 10_000
        create_incident('too many rows')
    end
end
```

```ruby
state :force_stop do
    aws.force_stop(my_server)
    if stopped? 
        transition :starting
    end
end
```

## Implementation

```ruby
while(thing = queue.shift())
    thing.think(thing.feel())
    queue.push(thing)
end
```



