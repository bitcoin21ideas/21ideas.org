---

title: "Все о мультисиг"
h1: "Все о мультисиг"
cover: /img/multisig/cover.png
description: "Этот обзор познакомит вас с различными аппаратными кошельками и поможет в дальнейшем выборе устройства для холодного хранения монет."
url: multisig
date: 2023-03-09
bookHidden: false
bookToc: true
bookFlatSection: false
weight: 6
---

Эта статья расскажет почему мультисиг является лучшим подходом для длительного холодного хранения, и как получить максимальную выгоду от его использования.

{{< hint btc >}}
Перевод и адаптация [статьи](https://unchained.com/features/what-is-multisig) Unchained подговтовлены [Тони⚡️](https://njump.me/npub10awzknjg5r5lajnr53438ndcyjylgqsrnrtq5grs495v42qc6awsj45ys7)
{{< /hint >}}

Когда речь заходит о хранении биткоина, обеспечение безопасности монет с помощью нескольких подписей - мультисиг - широко признано одним из самых безопасных методов. Эта схема позволяет устранить риски, вызываемые биржами и кастодианами (сторонними хранителями ваших монет), и одновременно решает наиболее распространенные проблемы, с которыми сталкиваются держатели биткоина. В этой статье мы расскажем о том, почему вам следует самостоятельно хранить собственные ключи, как выглядит стандартное хранение монет с одной подписью и почему мультисиг является лучшим методом для долгосрочного холодного хранения.

## Почему стоит самостоятельно хранить свои ключи?

Интерес к биткоину обычно начинается с признания его в качестве альтернативного денежного инструмента, который исправляет некоторые из очевидных недостатков привычных “денег”, таких как инфляция, цензура и возможность конфискации. По мере роста убежденности в важности переноса собственного богатства в биткоин многие сразу же сталкиваются с вопросом безопасного хранения монет.

В первую очередь стоит избегать кастодиальных решений. Причина проста: бизнесы и институты, хранящие фиатные валюты (банки, брокерские конторы и т. д.), могут предложить определенные гарантии, которых не могут дать кастодианы биткоина. Например, государственные программы обеспечивают страховку на случай потери депозитов клиентов, и эти обязательства всегда можно выполнить. Предложение биткоина строго ограничено[^1] 21 миллионом монет[^2]. В то время,  как страховка фиата обычно осуществляется за счет печати новых токенов, в Биткоине это невозможно. Соответственно, вы лишаетесь преимуществ кастодиального хранения, предлагаемых традиционными сервисами и остаетесь лишь с недостатками - невозможностью управлять собственными средствами, вероятностью конфискации, повышенным интересом хакеров к крупным суммам, хранящимся на кошельках кастодиана и повышенным риском взлома или краха.

Отказ от кастодиального хранения подразумевает самостоятельную опеку. В мире Биткоина принадлежность монет определяется тем, кто контролирует приватные ключи. Именно приватные ключи необходимы для расходования монет. Если вы купили биткоин на бирже и не вывели его на собственный кошелек, то биткоин остается под контролем биржи, и все, что у вас есть, - это обещание, а не реальные биткоины. Как говорится, "не ваши ключи - не ваши биткоины".

Владеть собственными ключами означает защищать секретную информацию, ведь приватный ключ - это не что иное, как информация: случайно сгенерированные данные, которые должны оставаться в тайне, и которые невозможно  угадать или подобрать. Сгенерировать приватный ключ несложно. Это можно сделать на ноутбуке или в мобильном приложении. Но чтобы быть уверенным, что ваш ключ никогда не попадет в интернет, стоит использовать аппаратный кошелек. 

{{< hint info >}}
С подробным сравнением 10 лучших аппаратных кошельков можно ознакомиться в [этой статье](/hwws).
{{< /hint >}}

Переживать по поводу хранения собственных биткоин-ключей вполне нормально. Люди часто теряют как информацию, например пароли, так и физические предметы, такие как солнечные очки или ключи от машины. Если вы беспокоитесь, что можете потерять ключи от своих биткоинов, а значит, и доступ к своим средствам, это опасение вполне обосновано! Однако Биткоин предлагает решение, которое обеспечивает дополнительную защиту на случай, если вы допустите ошибку и потеряете какую-то часть информации.

## Что такое одноподписная схема?

Чтобы понять, что такое мультисиг, важно сначала разобраться в более простом и распространенном методе хранения биткоинов - однодписной схеме. В этом подходе используется всего один приватный мастер-ключ, который может генерировать адреса для получения биткоинов. Если биткоин отправляется на один из этих адресов, сумма засчитывается в баланс кошелька, и отправить эти средства дальше можно только подписав транзакции приватным ключом.


{{% image "/img/multisig/examples.png" %}}
_Несколько примеров кошельков, обычно использующихся с одной подписью_
{{% /image %}}

Владелец приватного ключа может одобрить вывод средств, используя ключ для криптографической подписи транзакции. Это можно сравнить с физической подписью. Разница здесь заключается в том, что криптографическую подпись невозможно подделать. Процедура осуществляется вашим программным или аппаратным кошельком. Затем подписанная транзакция транслируется в сеть Биткоин, где она будет признана действительной только в том случае, если используется валидная подпись.

Преимуществом одноподписных схем является простота настройки, а также довольно быстрый и удобный доступ к выводу средств. Комиссия за транзакции, подписанные одной подписью, также обычно ниже, чем в мультисиг.

Однако главный недостаток этого подхода заключается в том, что одна подпись является единой точкой отказа. Здесь можно выделить две основные потенциальные проблемы:

- Уязвимость к краже: Если ваш приватный ключ окажется в руках злоумышленника, тот получит полный контроль над вашими биткоинами.

- Уязвимость к потере: Если вы потеряете информацию о своем приватном ключе (по неосторожности или в результате стихийного бедствия), вы не сможете распоряжаться своими биткоинами, то есть фактически перестанете ими владеть. 

В попытке нивелировать эти проблемы были созданы различные механизмы. 

Внедрение таких инструментов, как парольные фразы BIP 39 или Seed XOR, может помочь решить первую проблему, но в результате усугубляет вторую. Другой инструмент, называемый схемой разделения секрета Шамира, может улучшить ситуацию с обеих сторон, но проблема единой точки отказа возвращается, когда приходит время подписывать транзакцию.

В результате многие пользователи обращаются к схемам мультисиг как к золотому стандарту устранения единых точек отказа.

## Чем уникален мультисиг?

Биткоин-кошелек с мультиподписью - это метод защиты монет, который может требовать подписи несколькими приватными ключами. Подмножество этих ключей необходимо для подписи траты любых монет, поступивших на данные адреса.

Такая структура популярно описывается как кворум m-из-n. M определяет количество приватных ключей, необходимых для подписи, а N - общее количество приватных ключей, которые могут быть использованы для подписания транзакций.


{{% image "/img/multisig/m-of-n.png" %}}
_Кворум m-из-n представляет собой количество ключей, необходимых для подписи, и общее количество ключей в мультисиг-системе._
{{% /image %}}

Например, кворум 2-из-2 означает, что задействованы два разных приватных ключа, и для вывода биткоинов, полученных в рамках данной схемы, требуются подписи обоих ключей. Такой подход можно сравнить с решением, используемым для доступа к депозитным ячейкам в банке. Как правило, для открытия таких ячеек требуется два ключа, один из которых находится у вас, а другой - у банка. Существуют и древние примеры подобных подходов.

В качестве альтернативы можно создать кворум 1-из-2, когда для одобрения расходования требуется только один из двух задействованных ключей. Или можно создать кворум, включающий более двух ключей, например 2-из-3. Это будет означать, что в системе существует три ключа, и любая комбинация двух из них может одобрить расходование биткоинов.

Мультисиг-кворумы настраиваются в соответствии с потребностями пользователя, поэтому их можно расширить практически до любого размера: 5-из-6, 2-из-9 или любое другое сочетание. Однако некоторые кворумы значительно популярнее других. 2-из-3 и 3-из-5 являются наиболее распространенными схемами для защиты биткоина в холодном хранилище; о них мы и расскажем ниже.

{{% image "/img/multisig/setups.png" %}}
_Наиболее распространенные кворумы: 2-из-3 и 3-из-5. В обоих случаях соблюдается баланс между сложностью и безопасностью._
{{% /image %}}

## Зачем использовать мультисиг?

Переход от одноподписной схемы к схеме мультисиг означает использование большего количества ключей, а значит, и усложнение процесса. Стоит ли оно того? Давайте рассмотрим некоторые преимущества и недостатки этого подхода.

### Повышенная безопасность

Ранее мы обсудили некоторые из самых серьезных проблем, связанных с использованием одной подписи. К ним относятся единые точки отказа, такие как кража, потеря или уничтожение вашего приватного ключа. Чем может помочь мультисиг?
Некоторые мультисиг-кворумы внедряют в схему избыточность. Это гарантирует отсутствие отдельных элементов, угрожающих вашим средствам в случае непредвиденных обстоятельств. Даже если один из ваших приватных ключей окажется у злоумышленника, этого не будет достаточно для кражи ваших биткоинов. Кроме того, если один из ваших ключей будет утерян или уничтожен, вы сможете восстановить доступ к своим биткоинам, используя оставшиеся ключи. Все, что вам останется сделать - это настроить новую схему хранения и перевести средства на новый кошелек.

{{< hint info >}}
Мы рекомендуем позаботиться о создании “аварийного” кошелька заранее, чтобы в случае непредвиденной ситуации вам не пришлось в стрессовом состоянии генерировать ключи для переноса своих сбережений. Подробнее об этом читайте в нашем посте [здесь](https://t.me/bitcoin21ideas/2934).
{{< /hint >}}

Однако не все мультисиг-кворумы обеспечивают такую защиту. Кворум 1-из-n (например, 1-из-2 или 1-из-5) не обеспечивает подобной защиты от кражи, ведь для траты биткоинов достаточно одного ключа. Злоумышленнику все же понадобится файл, хранящий подробности мультисиг-схемы, но такие кворумы все же менее надежны, чем требующие несколько подписей для распоряжения монетами. С другой стороны, кворум n-из-n (например, 2-из-2 или 5-из-5) подразумевает, что если любой из ключей будет потерян или уничтожен, вы больше не сможете потратить свои биткоины.

Схемы, которые находятся между этими двумя крайностями, являются оптимальным вариантом обеспечения безопасности монет как от потери, так и от кражи. Наименее сложная схема, удовлетворяющая обе цели, - это 2-из-3. Этот подход также является наиболее популярным мультисиг-кворумом для защиты биткоинов. Кворум 3-из-5 также довольно популярен, но, будучи более сложным, он является менее привлекательным для большинства пользователей. Хотя схема 3-из-5 может обеспечить дополнительную избыточность, то же самое верно и для схем 4-из-7, 5-из-9 и так далее. Как правило, такие комплексные схемы имеют смысл для владельцев бизнесов или топ-менеджеров крупных корпораций.


{{% image "/img/multisig/graph.png" %}}
_Некоторые схемы могут подвергать вас риску кражи, а другие - риску потери. Мультисиг 2-из-3 защищает вас от обоих рисков, привнося при этом минимум усложнений._
{{% /image %}}

Если вы хотите получить максимальный эффект от защиты, обеспечиваемой системой мультисиг, храните все ключи в географически отдаленных локациях. Таким образом несколько ключей не смогут оказаться скомпроментированными одновременно. 

{{< hint info >}}
Подробнее о лучших практиках обеспечения безопасности сид-фраз читайте в [этом материале](/seed-security/).
{{< /hint >}}

Чем менее сложной будет ваша мультисиг-система, тем проще будет создать эффективную систему хранения ключей. 

### Дополнительные возможности применения

Мультисиг предлагает не только новые варианты хранения для индивидов. Эта схема способна принести пользу даже группам людей. Структуры, в которых разные участники владеют разными ключами в рамках мультисиг-кворума, предлагают некоторые новые возможности. Давайте вкратце рассмотрим несколько примеров.

**Управление казной**
Если компания, правительство или другая организация хочет грамотно хранить свои биткоины, без мультисига не обойтись. Не только из необходимости в повышенной безопасности, но и чтобы убедиться, что люди в организации имеют достаточные полномочия для расходования средств от имени группы.

Предположим, комитет или законодательный совет состоит из 9 человек, и эта группа отвечает за управление биткоин-казной. Если каждый член группы получит приватный ключ, они могут настроить свою структуру таким образом, чтобы определенный порог членов группы подписывал вывод средств из казны. Для расходования средств может потребоваться небольшая часть членов группы (3 из 9), или большинство (5 из 9), или даже супербольшинство (6 из 9).

Группа может решить наделить особых членов несколькими ключами, предоставляя им тем самым дополнительные полномочия по расходованию средств.

**Залог, минимизирующий доверие**
Многие держатели биткоина хотят использовать покупательную способность своих монет, при этом не продавая их. Во многих юрисдикциях продажа биткоинов облагается налогом. Более того, продавая биткоины вы рискуете упустить будущий рост этого актива.

Популярным решением этой дилеммы является кредит под залог биткоинов, обычно создаваемый с помощью мультисиг-кворума 2-из-3. Владелец биткоина может занять наличные у кредитора после внесения своих биткоинов в мультисиг-кошелек, где заемщик хранит один ключ, кредитор - второй ключ, а третья сторона - арбитр - третий ключ. Для вывода биткоина из кошелька требуется два ключа.


{{% image "/img/multisig/lend.png" %}}
_Некоторые схемы мультисиг позволяют трем сторонам совместно управлять кошельком, что делает возможными выдачу кредитов под залог._
{{% /image %}}

После погашения кредита заемщик и кредитор могут использовать свои ключи для подписания соглашения о возврате биткоина под полный контроль заемщика. Если кредит не погашен, биткоин может быть передан под полный контроль кредитора. Если возникает спор или один из участников не желает сотрудничать, арбитр может рассмотреть ситуацию и помочь оправданной стороне. 

При такой модели кража средств невозможна без сговора двух держателей ключей, что разрушит репутацию обоих субъектов. Такая структура называется "минимизацией доверия", что является существенным улучшением по сравнению с полным доверием к одному хранителю. Она также гарантирует, что биткоин не будет повторно заложен и в любой момент может быть передан на полное хранение законному владельцу.

{{< hint info >}}
Кредиты под залог биткоина - это услуга, предлагаемая платформой Hodl Hodl. Вы можете зарегистрироваться на платформе [по нашей реферальной ссылке](https://hodlhodl.com/join/TONYB), чтобы получать скидку на комиссии и поддерживать проект 21 идея с каждой покупкой или продажей биткоина на p2p-платформе. Ссылка на лендинг-платформу не является реферальной: https://lend.hodlhodl.com/.
{{< /hint >}}


## Компромиссы схемы мультисиг

Как уже отмечалось ранее, использование схемы мультисиг вынуждает пользователей идти на определенные компромиссы. 

Во-первых, схемы мультисиг усложняют процесс взаимодействия с протоколом Биткоин. С бóльшим количеством ключей появляется больше составляющих, нуждающихся в вашем внимании, и каждая составляющая в идеале должна храниться в отдельном месте. Мультисиг усложняет отправку биткоинов с кошелька, что хорошо для предотвращения несанкционированного доступа, но может доставлять неудобства, когда вам действительно необходимо переместить средства.

Еще один минус - более высокие комиссии за транзакции. Если вы хотите потратить свои биткоины, это, как правило, обойдется вам дороже, чем если бы вы использовали кошелек с одной подписью. Размер комиссий зависит от ряда факторов, но в среднем стоимость отправки растет пропорционально сложности кворума. Другими словами, одноподписная схема будет дешевле, чем мультисиг 2-из-3, а мультисиг 2-из-3 будет дешевле, чем 3-из-5.

С другой стороны, обновление Taproot в 2021 году позволило сделать так, чтобы мультисиг-транзакции были неотличимы от одноподписных. Это означает, что они будут стоить одинаково, и никаких дополнительных сборов для мультисиг-кворумов не будет! Однако на момент написания статьи обновление еще не получило широкого распространения.

Популярная стратегия, позволяющая использовать преимущества защиты мультисиг, минимизируя ее недостатки, заключается в том, чтобы использовать оба подхода к хранению монет. Например, вы можете:

1. Хранить бóльшую часть своих биткоинов на долгий срок, используя холодный кошелек и схему мультисиг
2. Держать при этом гораздо меньшую сумму биткоинов на горячем программном кошельке с одной подписью. 

Таким образом, вы можете быть спокойны, зная, что бóльшая часть вашего состояния защищена наилучшим образом, и в то же время вы можете легко отправлять и получать небольшие суммы более удобным способом.


{{% image "/img/multisig/approaches.png" %}}
_Мы рекомендуем использовать горячий кошелек с одной подписью для ежедневных трат и холодное мультисиг-хранилище для долгосрочных накоплений._
{{% /image %}}

## Мультисиг “сделай сам”

Впервые запустив схему мультисиг, большинство пользователей удивляются тому, насколько прост этот процесс, особенно если они уже знакомы с использованием singlesig. Тем не менее, прежде чем приступить к работе, стоит сравнить несколько способов.

Существуют бесплатные программы с открытым исходным кодом, которые помогут вам самостоятельно создать мультисиг-кошелек. Примерами таких программ являются Caravan, Sparrow Wallet, Electrum и Specter. 

Поскольку большинство биткоин-кошельков разработаны с учетом совместимости, если вы используете одну из этих программ для настройки своего мультисиг-кошелька, вы также сможете загрузить этот кошелек в одну из других программ (при условии, что у вас сохранен файл конфигурации кошелька). Это дает уверенность в том, что если  с используемым программным обеспечением что-то пойдет не так, ваши биткоины все равно будут в безопасности и доступны.

Вы можете настроить мультисиг полностью самостоятельно, используя несколько аппаратных (и/или программных) кошельков.

[^1]: 21 миллион не подлежит обсуждению: https://21ideas.org/21-million-ne-podlezhit-obsuzhdeniyu/ 

[^2]: Почему 21 миллион: https://21ideas.org/pochemu-21-million/ 
