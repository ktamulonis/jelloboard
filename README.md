# 1) Read the .env file carefully and change any user specific settings, such
#    as e-mail credentials and platform specific settings (check the comments).
#
# 2) Build and run the project with Docker Compose
docker-compose up --build
#
# 3) Reset and Migrate the database (run this in a 2nd Docker-enabled terminal)
# OSX / Windows users can skip adding the --user "$(id -u):$(id -g)" flag
docker-compose exec --user "$(id -u):$(id -g)" website rails db:reset
docker-compose exec --user "$(id -u):$(id -g)" website rails db:migrate
#
# 4a) Running Docker natively? Visit http://localhost:3000
# 4b) Running Docker with the Toolbox? Visit http://192.168.99.100:3000
#     (you may need to replace 192.168.99.100 with your Docker machine IP)
# jelloboard
