# Creating a serveless api with Route 53 -> API Gateway -> AWS Lambda

0. Make your lambda function for the api (many ways to do this)
1. Get a hosted zone
2. Get a wildcard certificate on AWS Certificate manager
3. Click add record to route 53
4. Create API Gateway -> RestAPI
5. Create resource, select Proxy Resource with resource path /{proxy+}
 (optional, select CORS)
6. On Method ANY, add Lambda integration type
7. Press deploy, new stage, name it something like prod
7. Custom domain names -> your wanted domain name (i.e. api.website.com)
8. Click radio button for new domain name, go on API mappings and map it to stage PROD
9. Go to your hosted zone in route 53, add an A record with the same name as in stage 7.
click alias, alias to API gateway api, enter region, press your API gateway
