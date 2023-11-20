1. Создайте новый проект в teamcity на основе fork.
2. Сделайте autodetect конфигурации.
<img src="images/1_1.png"/>
3. Сохраните необходимые шаги, запустите первую сборку master.
<img src="images/1_2.png"/>
4. Поменяйте условия сборки: если сборка по ветке `master`, то должен происходит `mvn clean deploy`, иначе `mvn clean test`.
<img src="images/1_3.png"/>
5. Для deploy будет необходимо загрузить [settings.xml](./teamcity/settings.xml) в набор конфигураций maven у teamcity, предварительно записав туда креды для подключения к nexus.
<img src="images/1_4.png"/>
6. В pom.xml необходимо поменять ссылки на репозиторий и nexus.
<img src="images/1_5.png"/>
7. Запустите сборку по master, убедитесь, что всё прошло успешно и артефакт появился в nexus.
<img src="images/1_6.png"/>
8. Мигрируйте `build configuration` в репозиторий.
<img src="images/1_7.png"/>
9. Создайте отдельную ветку `feature/add_reply` в репозитории.
10. Напишите новый метод для класса Welcomer: метод должен возвращать произвольную реплику, содержащую слово `hunter`.
11. Дополните тест для нового метода на поиск слова `hunter` в новой реплике.
12. Сделайте push всех изменений в новую ветку репозитория.
<img src="images/1_8.png"/>
13. Убедитесь, что сборка самостоятельно запустилась, тесты прошли успешно.
<img src="images/1_9.png"/>
14. Внесите изменения из произвольной ветки `feature/add_reply` в `master` через `Merge`.
<img src="images/1_10.png"/>
15. Убедитесь, что нет собранного артефакта в сборке по ветке `master`.
<img src="images/1_11.png"/>
16. Настройте конфигурацию так, чтобы она собирала `.jar` в артефакты сборки.
<img src="images/1_12.png"/>
17. Проведите повторную сборку мастера, убедитесь, что сбора прошла успешно и артефакты собраны.
<img src="images/1_13.png"/>
18. Проверьте, что конфигурация в репозитории содержит все настройки конфигурации из teamcity.
https://github.com/ivannikita/teamcity_repo/blob/main/.teamcity/Netology/buildTypes/Netology_ExampleTeamcity.xml
19. В ответе пришлите ссылку на репозиторий.
https://github.com/ivannikita/teamcity_repo/tree/main