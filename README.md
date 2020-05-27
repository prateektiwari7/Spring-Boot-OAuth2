<h3> Spring Security Demo</h3>

1. Get Authorisation from here 

        http://localhost:8080/oauth/authorize?client_id=javadevjournal&response_type=code&scope=user_info

2. Oauth Approval Options 

        Approve 
        Deny 
     
3. Get login code 

        http://localhost:8081/login?code=13428u)

4. Get Access Token 

        curl -X POST \
        http://localhost:8080/oauth/token \
        -H 'authorization: Basic amF2YWRldmpvdXJuYWw6MTIzNCQjQCE=' \
        -H 'cache-control: no-cache' \
        -H 'content-type: application/x-www-form-urlencoded' \
        -H 'postman-token: f24e14c3-a90a-4866-59ae-3691dfb3ea0a' \
        -d 'code=ntCgjD&grant_type=authorization_code&redirect_uri=http%3A%2F%2Flocalhost%3A8081%2Flogin&scope=user_info'

5. Use the Access token 

        curl -X GET \
          http://localhost:8080/api/customers/customer/1 \
          -H 'Authorization: Bearer f4e93f7c-59c3-4ca3-a5c3-0e74582b1b18' \
          -H 'cache-control: no-cache'