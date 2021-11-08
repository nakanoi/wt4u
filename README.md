# React/Rails/Nginx/puma/MySQL on Docker

![message](https://user-images.githubusercontent.com/72122101/140685724-1c155e30-c473-4700-9804-ac17572c0efc.png)

This is the repo which I rebuild [this repository](https://github.com/nakanoi/wanttotravel4you). I coded it with React + AWS Amplify, but I wanted to build backend API with Ruby on Rails.
So, I build this with React + Rails API + Nginx + MySQL on Docker compose.

## Tech

I used these techniques below.

### Backend
- [`Ruby on Rails`](https://github.com/rails/rails) - with API mode.
- [`Nginx`](https://nginx.org/) - as a reverse proxy.
- [`MySQL`](https://www.mysql.com) - Database.
- [`Rspec`](https://rspec.info/) - as a API test module.
- [`Devise token auth`](https://devise-token-auth.gitbook.io/devise-token-auth) - as a authentication module.
- [`Websocket(Actoin Calbe)`](https://guides.rubyonrails.org/action_cable_overview.html) - to build realtime chat fumction.

### Frontend
- [`React`](https://github.com/rails/rails) - with frontend.
- [`Nginx`](https://nginx.org/) - as a reverse proxy.
- [`material UI`](https://mui.com/) - as a UI design. This page's disign is terrible? I'm sorry... I'm not good at this.

### Container
- [`Docker, Docker compose`](https://www.docker.com/) - run 5 containers, which area for each service above.

## Versions
| | version |
----|----
| `Ruby` | `2.6.2` |
| `Ruby on Rails` | `6.1.4` |
| `React` | `17.0.2` |
| `Nginx` | `1.20.1` |
| `MySQL` | `5.7` |
| `Docker` | `20.10.9` |
| `Docker compose` | `1.27.4` |

If you want to see more details about packages or these versions, check [`package.json`]()

## Simple Start
1. Clone this repo.
```sh
git clone
```
2. Build containers.
```sh
cd wt4u
docker-compose up --build
```
3. Go into rails container, install gems and migrate files.
```sh
docker exec -it {Rails container ID} bash
bundle install
bundle exec rails db:migrate
```
4. Go into react container, install packages.
```sh
docker exec -it {React container ID} bash
yarn install
```
5. *You can experience my project.*

## How to Use
1. Sign up with your email address, name and passsword.
![signin](https://user-images.githubusercontent.com/72122101/140680425-63fec5f4-7979-4468-a0e9-da421a9ca2d4.png)
2. Sign in with 3 informations above.
![signin](https://user-images.githubusercontent.com/72122101/140684804-8c10b9fd-9f93-4a85-ae0b-9d438adab8f6.png)
3. Register yourself as a *tourist* or a *travel agent*.
![home_without_type](https://user-images.githubusercontent.com/72122101/140684837-79f6ff5f-b32d-49a8-85d2-d6f4495dcc23.png)
4. When you registered yourself as a *toursit*, you can post your travel request with details like date or prefecture.
![request](https://user-images.githubusercontent.com/72122101/140684859-69cf68e1-d664-4b87-8a7f-b682561ffc61.png)
5. When you registered yourself as a *tourist*, you have to register your *business type* and *area*.
6. You can contact to *tourist's request* in 4. If you want to start communication with its poster, click **CONTACT TO THIS REQUEST**. After that, you can see its room in [room list](http://localhost/rooms).
![allrequests](https://user-images.githubusercontent.com/72122101/140684941-4d43f88b-656e-4607-8af2-4b971fb07aa4.png)
7. Send messages with tourists in chat rooms. Because this system use Websocket protocol, the chat is realtime.
![rooms](https://user-images.githubusercontent.com/72122101/140685611-237e3fa1-d463-4a81-9521-09fd9232d27e.png)
8. Communicate with your client!.
![message](https://user-images.githubusercontent.com/72122101/140685724-1c155e30-c473-4700-9804-ac17572c0efc.png)

## License

MIT

**Thank you for visiting my repo!**
