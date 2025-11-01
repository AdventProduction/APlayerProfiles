# Предисловие
APlayerProfiles - Плагин, добавляющий профиль и рейтинг игрока.

**Версия: 1.16.5-1.21.4 (Paper)**

> [!IMPORTANT]
> Плагин требует PlaceholderAPI

# Функционал
Зажав шифт и ПКМ по игроку, откроется его профиль, где любой может оценить игрока (поставить лайк или дизлайк).
Исходя из кол-ва лайков и дизлайков складывается общий рейтинг игрока, он может быть как положительным так и отрицательным.
Плагин позволяет оценить одного игрока только один раз, но есть и возможность отменить свой выбор и оценить заново.

# Конфиг
Базовый конфиг представлен ниже
```
messages:
  setLike: '&aВы поставили лайк игроку %player%'
  setDislike: '&cВы поставили дизлайк игроку %player%'
  already: '&cВы уже голосовали за этого игрока!'
  offline: '&cИгрок %player% не в сети'
  reload: '&aКонфиг перезагружен'
  permission: '&cНет прав'
  noVote: 'Чтобы отменить свой голос сначала нужно проголосовать'
  voteCancelled: 'Вы отменили голос за игрока %player%'
sound:
  like:
    enable: true #Включить/выключить звук
    sound: entity.player.levelup
    volume: 1.0
    pitch: 1.0
  dislike:
    enable: true #Включить/выключить звук
    sound: block.note_block.bit
    volume: 1.0
    pitch: 1.0
  vote_cancelled:
    enable: true #Включить/выключить звук
    sound: block.note_block.bit
    volume: 1.0
    pitch: 1.0
rating:
  positive: "&#40EA11" # Цвет для положительного числа
  neutral: "&#968385" # Цвет когда рейтинг равен нулю
  negative: "&#FF001F" # Цвет для отрицательного числа


MainProfileMenu:  #Главное меню профиля
  name: "Профиль игрока &c%player%"
  size: 45
  slots:
    filler:
      material: GRAY_STAINED_GLASS_PANE
      name: ' '
      glow: true
      slot: [0, 1, 7, 8, 9, 17, 27, 35, 36, 37, 43, 44]
      itemflags: []
    like:
      material: GREEN_TERRACOTTA
      name: '&aНажмите, чтобы поставить лайк'
      glow: true
      slot: 20
      action:
        type: like
    dislike:
      material: RED_TERRACOTTA
      name: '&cНажмите, чтобы поставить дизлайк'
      glow: true
      slot: 24
      action:
        type: dislike
    cancel_vote:
      material: red_concrete
      name: "&6Отмена голоса"
      slot: 31
      action:
        type: cancel_vote
    skull:
      material: SUNFLOWER
      name: "&e%player%"
      lore:
        - '&bЛайков - &a%like%&7/&bДизлайков - &c%dislike%'
        - '&aРейтинг: &b%rating%'
      slot: 22
```

# Возможности
В конфиге можно настроить сообщения, звук при нажатии на определенную кнопку, цвет рейтинга (когда он >0, =0 и <0), а так же саму меньшку профиля.
В менюшке можно добавить предмет, его название, описание, слот, действие, свечение и флаги. 

# Плейсхолдеры
В плагине поддерживаются плейсхолдеры.
А так же есть свои:
%aplayerprofiles_like% - выводит кол-во лайков игрока
%aplayerprofiles_dislike% - выводит кол-во дизлайков игрока
%aplayerprofiles_rating% - выводит рейтинг игрока по такой формуле: like - dislike. Соответственно в своем цвете, как вы указали в конфиге

# Кратко о командах и разрешениях

> ### Команды
**/aplayerprofiles reload** - Перезагрузить конфиг. 

> ### Разрешения
**aplayerprofiles.*** - Доступ ко всем командам.\
**aplayerprofiles.reload** - Доступ к /aplayerprofiles reload.

# База Данных
Информация о том, сколько лайков и дизлайков у того или иного игрока, хранится в специальном файле likes.yml.

# P.S.
> [!NOTE]
> Плагин является платным, купить его Вы можете по ссылке ниже.\
> https://funpay.com/lots/offer?id=56564582
