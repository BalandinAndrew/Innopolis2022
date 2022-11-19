# Innopolis2022
RussianChampionship, Kazan
Решение выполнено в два этапа:
Первый этап - многоклассовая классификация на CatBoost. Выполнялась по 5 подвыборках по всем входным данным + данные геокоординат, извлеченные из текстового файла.
Полученные результаты суммированы в модуле "Замена", модами по каждой строке выбрана результирующая сабмиссия с результатом 0.972297 на лидерборде. Это - основной опорный прогноз.
Второй этап - корректирующий. Выполнялся, в целом - классификациями на Xgboost. Поскольку на предварительном прогнозе по подвыборкам выявлено, что класс 5 не имеет сомнений в прогнозах, а класс 3 - практически не имеет (значенияя по классам одинаковы во всех подвыборках) - они последовательно исключались из теста и трейна. Прогнозы по сокращенным подвыборкам, совмещенные с теми, где классы предсказаны однозначно, дали результаты 0.972440 и 0.972953, высшие чем начальный прогноз. Выполнение моды и замен по классам на этих трех прогнозах позволили достичь результата 0.976187. В заключении был произведен перебор по каждому из классов бинарной классификацией по xgboost по принципу "один класс против всех". Положительные результаты дал перебор по двум классам - 0 и 5, результаты по другим классам остались неизменными. 
Итоговый прогноз показал результат 0.980132 на ЛБ.
Финальная сбмиссий приведена в корне лидерборда.
