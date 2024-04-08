---
title: "Приватность UTXO"
h1: "UTXO, адреса и CoinJoin: Обеспечение приватности в экономике Биткоина"
description: ""
cover: /img/utxo/private-piggy-cover.png
url: protocol/utxo-3
date: 2022-10-03
bookFlatSection: false
bookToc: true
bookHidden: false
weight: 3
---

{{< expand "Оглавление" "..." >}}

## Что такое UTXO и как ими управлять?

1. [Что такое UTXO, и почему они важны?](/protocol/utxo-1)

2. [Больше UTXO — больше сложностей: как избежать высоких комиссий и ошибки подписи транзакции](/protocol/utxo-2)

3. [UTXO, адреса и CoinJoin: Обеспечение приватности в экономике Биткоина](/protocol/utxo-3)

{{< /expand >}}

{{< hint btc>}}
Перевод [статьи](https://unchained.com/blog/bitcoin-utxo-privacy) Unchained. [Поддержать проект](/contribute/).
{{< /hint >}}

Ранее в этой серии, посвященной UTXO, были опубликованы две статьи. [Первая статья](/protocol/utxo-1) служит введением в суть UTXO и объясняет, почему активное управление ими важно для всех, кто хранит биткоины под собственным контролем. [Вторая статья](/protocol/utxo-2) посвящена тому, как стратегически подходить к количеству UTXO, которые вы храните, чтобы снизить будущие издержки при проведении транзакций и предотвратить ошибки в процессе подписи.

Эта статья посвящена тому, как управлять UTXO, чтобы сохранить приватность. Поскольку все Биткоин-транзакции публично записываются в блокчейн, от того, как вы подходите к отправке и получению биткоинов, зависит, какую информацию вы раскрываете другим людям. Понимание того, как работают UTXO и адреса кошельков, и внимательное отношение к тому, как вы с ними взаимодействуете, может ограничить возможности сторонних наблюдателей отслеживать ваше поведение и баланс кошелька.

Для начала мы рассмотрим, какая информация о транзакциях всегда находится в открытом доступе в блокчейне. Затем мы расскажем о некоторых методах, которые можно использовать для сохранения приватности при получении и отправке биткоинов. И наконец, мы обсудим, что делать, если вы подозреваете, что ваши действия отслеживает злоумышленник, и вы сможете помешать ему совать нос в чужие дела.

## Публично доступная информация

Первый шаг к тому, чтобы научиться защищать свою приватность, — это понимание того, какая информация находится в открытом доступе для всех желающих. Хотя Биткоин можно использовать совершенно анонимно, он также заведомо является очень прозрачной системой, чтобы пользователи могли проверить соблюдение всех правил протокола (например, ограничение в 21 миллион единиц) и подтвердить получение платежей, не доверяя третьей стороне. Поэтому изучение того, как биткоин-адреса функционируют в блокчейне, — важнейший фундамент, на котором следует строить свою работу.

### UTXO находятся в адресах

UTXO и адреса — это не одно и то же. Их часто объединяют, и мы скоро увидим, почему, но важно воспринимать их отдельно. Если UTXO можно представить как отдельный кусочек биткоина, то адрес — это место, где хранится UTXO. Адрес может содержать ни одного UTXO, один UTXO или множество различных UTXO.

Биткоин-кошельки могут генерировать множество адресов для получения UTXO. Фактически, ваш кошелек может сгенерировать больше уникальных адресов, чем вы когда-либо сможете использовать! Существует так много комбинаций символов, которые могут быть выбраны для создания адреса, что нет никаких реальных шансов на то, что ваш кошелек сгенерирует адрес, который также сгенерирован кем-то другим.

### Адреса отслеживаются в блокчейне

Блокчейн Биткоина можно рассматривать как публичный реестр, который отслеживает адреса, содержащие UTXO, а также стоимость каждого UTXO. Однако блокчейн не может знать, каким кошелькам — или каким людям — принадлежат эти адреса и UTXO.

Когда вы проверяете баланс своего Биткоин-кошелька, программное обеспечение использует ваш открытый ключ (или открытые ключи, если используется [multisig](/multisig-1)) для получения списка адресов, на которые ранее могли быть отправлены биткоины. Затем будет просканирован блокчейн, чтобы проверить, не содержит ли какой-либо из этих адресов UTXO. Если они есть, то кошелек сложит количество контролируемых вами биткоинов и выведет сумму на экран. Другими словами, информация о том, что ваши адреса принадлежат одному кошельку, не является публичной в блокчейне, но ее может узнать любой, у кого есть соответствующий открытый ключ (ключи).

{{< image src="/img/utxo/privacy-1-en.png" />}}

Эта визуализация не является точным отображением блокчейна, но может быть полезна для того, чтобы представить, где хранится определенная информация.

## Обеспечение приватности при получении биткоинов

Ваш кошелек может генерировать адреса, будучи полностью отключенным от Интернета. Другие люди не могут узнать, какие адреса принадлежат вам, если у них нет доступа к вашему открытому или закрытому ключу (ключам).

Однако если вы попросите кого-то отправить биткоины на ваш кошелек, вы должны сообщить отправителю один из своих адресов. Как только вы это сделаете, вы навсегда выдадите отправителю, что этот адрес принадлежит именно вам. Затем отправитель может поделиться этой информацией с другими людьми. Если вы не доверяете отправителю полностью, часть вашей приватности была утрачена. В блокчейне всегда можно проследить, сколько биткоинов вы храните на этом адресе.

Если вы переводите биткоины с раскрытого адреса на новый адрес (контролируемый вами, либо кем-то другим), эта вторичная транзакция также публично записывается в блокчейн. Тот, кто отслеживает вашу деятельность, может не только увидеть, что ваши биткоины переместились, но и узнать новый адрес (адреса), на который были отправлены биткоины. Можно предположить, что все новые адреса также принадлежат вам, хотя у вас может быть возможность правдоподобного отрицания этого предположения.

Сколько бы раз вы ни перемещали биткоин на новые адреса, все равно остается след, ведущий к вашему раскрытому адресу. Однако можно использовать определенные техники, которые помогут оборвать этот след, о чем мы расскажем далее в этой статье.

На данном этапе ключевым моментом является следующее: не забывайте о негативных последствиях повторного использования адресов. Использовать совершенно новый адрес каждый раз, когда вы получаете биткоины — особенно от нового отправителя, — разумно. Если вы раскроете адрес отправителю A и получите 0.2 BTC, а затем раскроете тот же адрес отправителю B и получите 0.3 BTC, оба отправителя смогут увидеть, что вы получили 0.5 BTC из нескольких разных источников.

{{< image src="/img/utxo/privacy-2-en.png" />}}

Именно поэтому многие предпочитают получать только один UTXO на один адрес. Каждый раз, когда вы хотите получить биткоины, вы можете использовать новый адрес, сгенерированный вашим кошельком, без какой-либо дополнительной платы. Отправитель не может связать новый адрес с адресами, которые вы использовали ранее, если только другая информация не была раскрыта ранее.

## Обеспечение приватности при отправке биткоинов

Когда вы отправляете кому-то биткоины, он может увидеть, с какого адреса (адресов) они пришли. Это еще один способ, с помощью которого определенные адреса могут навсегда ассоциироваться с вашей личностью.

Как только вы выводите биткоины с адреса, лучше никогда больше не использовать этот адрес. Когда вы тратите средства с Биткоин-адреса, вы также публично раскрываете способ создания адреса (например, multisig 2-из-3) и индивидуальные открытые ключи, использованные для создания этого адреса. Как уже говорилось в предыдущем разделе, ваш кошелек всегда сможет предоставить вам новые адреса, поэтому редко возникает необходимость повторно использовать старый адрес.

При отправке биткоинов необходимо учитывать некоторые нюансы. Во-первых, вам следует помнить о том, какие адреса вы можете объединить, предоставляя входы для транзакции, поскольку это может раскрыть новую информацию о людях, с которыми вы проводили транзакции в прошлом. Во-вторых, различные размеры UTXO, которые вы выбираете для транзакции, могут определить, сколько сдачи вы получите обратно и, следовательно, сколько биткоинов вы покажете как все еще принадлежащие вам. Давайте рассмотрим эти понятия более подробно.

### Предотвращение нежелательных комбинаций адресов

Предположим, вы берете несколько UTXO из своего кошелька, которые находятся на разных адресах, и объединяете их в качестве входов для одной транзакции. В этом случае вы показываете свое право собственности на _все_ адреса, участвующие в транзакции. Если кто-то, пытающийся отследить вас, знал только об одном из адресов, то теперь он будет знать и об остальных. Тогда можно посмотреть в блокчейн, чтобы увидеть историю этих адресов и узнать больше о вашей деятельности.

Рассмотрим пример:

{{< image src="/img/utxo/privacy-3-en.png" />}}

На приведенном выше рисунке отправитель A отправил вам 0.2 BTC, отправитель B — 0.3 BTC, а отправитель C — 1.1 BTC. Поскольку вы каждый раз использовали разные адреса, ни один из отправителей не знает о том, сколько биткоинов находится в вашем распоряжении, помимо той суммы, которую они сами вам отправили.

Однако, как только вы возьмете UTXO с каждого адреса и объедините их, чтобы отправить куда-то 1.6 BTC, ваши три адреса окажутся связаны. Если отправитель A был злоумышленником, отслеживающим ваше поведение, он узнал, что два других адреса, предоставляющие входы для транзакции, скорее всего, принадлежат вашему кошельку. Он также может увидеть, что на этих адресах в какой-то момент находилось в общей сложности 1.4 BTC, и он может узнать, кто владел этими биткоинами до того, как они попали к вам (возможно, узнав о ваших отношениях с отправителем B и отправителем C).

Помните, что консолидация UTXO, о которой шла речь в двух предыдущих статьях этой серии, часто подразумевает объединение UTXO с разных адресов. Иллюстрация выше может представлять собой консолидацию UTXO, если адрес получателя — это просто новый адрес вашего кошелька. Из-за соображений конфиденциальности некоторые люди очень избирательно относятся к тому, какие UTXO они выбирают для консолидации, а другие предпочитают полностью избегать консолидации.

### Предотвращение большой суммы сдачи

В [нашей первой статье о UTXO](/protocol/utxo-1) мы обсуждали проблему для приватности, возникающую при использовании большого UTXO для отправки кому-то гораздо меньшей суммы биткоинов. Например, если вы используете UTXO стоимостью 0.9 BTC, чтобы отправить кому-то 0.2 BTC, вы также отправите оставшиеся 0.7 BTC себе обратно на новый адрес в качестве сдачи.

{{< image src="/img/utxo/privacy-4-en.png" />}}

Если получатель посмотрит транзакцию в блокчейне и увидит второй выход стоимостью 0.7 BTC, он может резонно предположить, что это ваша сдача. Тогда он может быть уверен, что вы все еще владеете как минимум 0.7 BTC, а это, в свою очередь, является информацией, которую вы предпочли бы не раскрывать.

Храня свои биткоины в меньших UTXO, у вас будет больше возможностей предотвратить попадание информации о значительных суммах на вашем балансе в руки других людей. Однако это может привести к тому, что вам придется объединять UTXO с разных адресов, чтобы достичь полной суммы, которую вы хотите отправить... что, как мы только что обсудили, также может быть плохо для вашей приватности.

Идеальное решение — точно определить, сколько биткоинов вы отправите другим людям в будущем; какие товары или услуги вы захотите купить на свои биткоины и сколько биткоинов они будут стоить в момент покупки. Если бы у вас была такая информация, вы могли бы хранить на одном адресе один UTXO с точной суммой, необходимой вам для оплаты, и вам никогда не пришлось бы беспокоиться об объединении адресов или получении сдачи. Очевидно, что на практике это неосуществимо.

Менее идеальная, но, возможно, лучшая альтернатива — хранить биткоины в UTXO разных размеров, чтобы у вас был широкий выбор вариантов, когда вы захотите отправить биткоины. Как и в случае с наличными в копилке или физическом кошельке, большинство людей будут иметь множество долларовых купюр разного номинала, а не одну купюру в 100 долларов или сотню купюр в 1 доллар.

## Восстановление анонимности с помощью CoinJoin

То, о чем мы рассказывали до сих пор, может натолкнуть вас на мысль, что обеспечение приватности при использовании Биткоина может быть довольно сложной задачей. Вам не только придется тщательно выбирать адреса и UTXO каждый раз, когда вы перемещаете биткоины, но и отслеживать каждый адрес, который вы когда-либо использовали для получения UTXO, и отмечать, кто был отправителем, который может связать этот адрес с вашей личностью. Это может показаться непосильной задачей, особенно если у вас есть несколько UTXO, которые вы получили очень давно и не можете с уверенностью вспомнить, кто их вам отправил.

К счастью, можно использовать очень мощный инструмент, чтобы изменить ситуацию против тех, кто пытается злонамеренно следить за вами. CoinJoin — это техника, которая позволяет вам вернуть утраченную приватность и, в некоторой степени, исправить ошибки, которые вы могли совершить в прошлом. Отправка биткоинов в CoinJoin запутает путь, ведущий к вам, и никому не удастся связать UTXO с вашей личностью.

Прежде чем проводить CoinJoin, необходимо ознакомиться с местными законами и правилами. Несмотря на то, что CoinJoin создан для повышения приватности обычных пользователей, есть подозрения, что он используется для отмывания денег, что является незаконным. Подобные подозрения сдерживают энтузиазм некоторых людей по отношению к этому в остальном безобидному инструменту. Стоит также отметить, что некоторые финансовые учреждения могут отказаться принимать биткоины, участвовавшие в CoinJoin.

### Как работает CoinJoin?

Концепция довольно проста: CoinJoin — это доверительное сотрудничество между несколькими людьми для создания транзакции. В самом простом виде каждый участник вносит равное количество биткоинов в качестве входа в транзакцию, а затем каждый получает обратно это количество биткоинов в качестве выхода.

Рассмотрим пример:

{{< image src="/img/utxo/privacy-5-en.png" />}}

Эта визуализация демонстрирует CoinJoin между вами и четырьмя другими участниками. Каждый участник берет 0.05 BTC с адреса, связанного с его личностью, и соглашается внести их в общую транзакцию (плюс комиссия). Когда транзакция завершается, каждый получает 0.05 BTC обратно в виде UTXO на совершенно новый адрес кошелька, который он контролирует. Пять новых адресов, на которые поступают UTXO, должны быть анонимными, и любой наблюдатель, просматривающий блокчейн, не будет иметь представления о том, какой из адресов-получателей принадлежит вам. Вероятность того, что каждый из адресов принадлежит вам, составляет всего 20 %.

Поскольку остальные четыре участника в конечном итоге потратят свои биткоины и могут раскрыть, какие адреса принадлежат им, адрес, принадлежащий вам, может стать менее замаскированным простым исключением. Однако с этим можно легко бороться, делая несколько CoinJoin или проводя CoinJoin с гораздо большим количеством участников.

Существует несколько различных реализаций CoinJoin, которые широко используются людьми по всему миру для анонимной координации этого процесса. Наиболее известные варианты — WabiSabi, Samourai Whirlpool и JoinMarket. Каждая реализация работает по-своему и имеет свои преимущества, поэтому прежде чем выбрать метод, проведите дополнительное исследование.

Также помните, что после перевода биткоинов через CoinJoin, они могут снова стать связанными с вашей личностью при последующих действиях. Например, отправив биткоины другому человеку и получив сдачу обратно, вы тем самым раскроете ее, пока она не будет включена в новый CoinJoin. Или, если вы используете биткоины в какой-либо финансовой организации, которой известна ваша личность, естественно, биткоины станут связаны с вами в глазах поставщика услуг.

{{% hint btc %}}
Узнать больше о различных реализациях CoinJoin, а так же ознакомиться с практическим пособием по Whirlpool, вы можете из [этой](/privacy/coinjoin) статьи.
{{% /hint %}}

## Заключение

Приватность — это обширная тема, и невозможно охватить все ее аспекты в одной статье. Однако мы хотим затронуть еще несколько вопросов. Многие люди, знакомящиеся с Биткоином, слышали утверждения о том, что пылевая атака, управление собственным узлом и использование сети Lightning влияют на вашу приватность. Давайте вкратце рассмотрим каждую из этих тем.

### Пылевая атака

Если вы когда-нибудь замечали, что в вашем кошельке появилась небольшая сумма биткоинов (обычно менее 1000 сатоши), но не знаете, откуда она взялась, то, скорее всего, вы подверглись так называемой "пылевой атаке". Этот термин звучит гораздо более пугающе, чем есть на самом деле.

Как правило, пылевая атака — это просто причудливая форма рекламы, которая никак не влияет на вашу приватность. Если вы когда-нибудь получите небольшое количество сатоши на контролируемый вами адрес, где уже хранятся биткоины, вы можете проигнорировать его. Когда вы будете выводить свои биткоины с этого адреса, вы можете либо включить крошечный UTXO в транзакцию, либо оставить его в кошельке.

С другой стороны, если вы когда-нибудь получите небольшое количество сатоши на пустой адрес, контролируемый вами, который ранее использовался, не трогайте этот UTXO при отправке биткоинов. Хотя такое случается редко и не представляет особой опасности, объединение этого UTXO с другими вашими биткоинами может раскрыть заинтересованным лицам ваше право собственности на другие адреса (см. предыдущий раздел "[Предотвращение нежелательных комбинаций адресов](/protocol/utxo-3/#%d0%bf%d1%80%d0%b5%d0%b4%d0%be%d1%82%d0%b2%d1%80%d0%b0%d1%89%d0%b5%d0%bd%d0%b8%d0%b5-%d0%bd%d0%b5%d0%b6%d0%b5%d0%bb%d0%b0%d1%82%d0%b5%d0%bb%d1%8c%d0%bd%d1%8b%d1%85-%d0%ba%d0%be%d0%bc%d0%b1%d0%b8%d0%bd%d0%b0%d1%86%d0%b8%d0%b9-%d0%b0%d0%b4%d1%80%d0%b5%d1%81%d0%be%d0%b2)"). Многие кошельки защищают вас от этого автоматически, по умолчанию не отправляя маленький UTXO.

### Запуск собственного узла

Чтобы проверить баланс своего кошелька или отправить биткоины, необходимо подключиться к сети Биткоина через узел. В мире насчитываются десятки тысяч узлов, которые и составляют сеть, и они общаются друг с другом, чтобы поддерживать децентрализацию Биткоина. 

Проведя небольшое исследование и не затратив много усилий и средств, вы можете запустить собственный узел Биткоина и подключиться к сети напрямую. Если у вас нет собственного узла, то при взаимодействии с Биткоин-кошельком вы будете вынуждены передавать информацию через чужой узел. Программное обеспечение кошельков использует узлы, к которым вы можете подключиться по умолчанию, но что, если вы не хотите, чтобы ваша приватность зависела от безопасности и честности стороннего узла? Вместо этого вы можете взять все в свои руки и отправлять и получать информацию только через свое собственное оборудование. Приватность — одна из [нескольких причин](/practice/bitcoin-node) рассмотреть возможность запуска собственного узла.

### Сеть Lightning

Отличный способ завершить эту серию о UTXO — обсудить Lightning Network. Lightning — это, безусловно, самая популярная технология второго уровня, созданная поверх Биткоина. Она позволяет проводить транзакции за пределами блокчейна, используя сеть из мультисиг-контрактов 2-из-2, называемых каналами.

Благодаря отсутствию блокчейна Lightning-платежи осуществляются быстрее (практически мгновенно) и с меньшими комиссиями за транзакции. Кроме того, они не записываются в публичный реестр. С точки зрения приватности это дает существенные преимущества. Отправка биткоинов через Lightning Network — это еще один метод, который может создать трудности для тех, кто пытается отследить, куда ушли ваши биткоины.

Однако сеть Lightning сложна и все еще относительно нова. Преимущества приватности далеки от совершенства, и обычно не рекомендуется вкладывать большие суммы биткоинов в Lightning Network по соображениям безопасности. Тем не менее, с каждым месяцем происходят улучшения; разработчики Lightning действительно находятся на переднем крае платежных технологий.

Многие из тем, затронутых в этой трилогии статей, не относятся к миру сети Lightning, поскольку UTXO не участвуют непосредственно в  Lightning-платежах. Тем не менее, базовый уровень Биткоина с наивысшей степенью защиты, который требует обычных транзакций в блокчейне, всегда будет актуален, а значит, и UTXO. Теперь, когда мы рассмотрели основы UTXO и компромиссы, связанные с управлением ими, вы будете гораздо лучше подготовлены к уверенной работе в Биткоин-экономике.

{{< expand "Оглавление" "..." >}}

## Что такое UTXO и как ими управлять?

1. [Что такое UTXO, и почему они важны?](/protocol/utxo-1)

2. [Больше UTXO — больше сложностей: как избежать высоких комиссий и ошибки подписи транзакции](/protocol/utxo-2)

3. [UTXO, адреса и CoinJoin: Обеспечение приватности в экономике Биткоина](/protocol/utxo-3)

{{< /expand >}}

### Поддержите переводчика

Поддержать переводчика можно, отправив немного сат в сети Лайтнинг:

{{% image "/img/btclinux-ln-qr.jpg" %}}
_LNURL1DP68GURN8GHJ7MRW9E6XJURN9UH8WETVDSKKKMN0WAHZ7MRWW4EXCUP0X9UX2VENXDJN2CTRXSUN2VE3XGCRQPNAPC6_
{{% /image %}}