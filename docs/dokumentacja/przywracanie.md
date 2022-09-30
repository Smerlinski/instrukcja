# Przywracanie definicji

Najpierw należy plik yaml danej definicji umieścić w `/home/ubuntu/.runner/_work/api-lagom/api-lagom/setup/import/_basic` a następnie przejść do `/home/ubuntu/.runner/_work/api-lagom/api-lagom` i uruchomić poniższe komendy:
1. >sbt docker:publishLocal
2. >docker-compose -f docker/setup.yml --project-name "instap" build
3. >docker-compose -f docker/setup.yml --project-name "instap" up -d