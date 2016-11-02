# Testing JWT

  - Project to test [knock](https://github.com/nsarno/knock) one implementation of [JWT](https://github.com/jwt/ruby-jwt)

## Testing

With server running:
```
./bin/setup && ./bin/rails s
```

Execute:
```
$ curl localhost:3000/teste 
# Filter chain halted as :authenticate_user rendered or redirected
# Completed 401 Unauthorized in 1ms (ActiveRecord: 0.1ms)

curl -X POST -d 'auth[email]=user@example.com&auth[password]=mudar123' http://localhost:3000/user_token
# Completed 201 Created in 67ms (Views: 0.1ms | ActiveRecord: 0.1ms)
# {
#   "jwt" : "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9"
# }
# with this token:

curl -H "Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9" localhost:3000/teste
# Completed 200 OK in 132ms (Views: 130.8ms | ActiveRecord: 0.1ms)
```
