# MAC OS:

#### BASH
* ls - показывает, что в директории
* pwd - показывает путь к текущей директории в виде строки
* mkdir - новая папка


#### Убираем диски с рабочего стола:
defaults write com.apple.Finder ShowHardDrivesOnDesktop NO && killall Finder

#### Возвращаем диски на раб стол:
defaults write com.apple.Finder ShowHardDrivesOnDesktop Yes && killall Finder

#### Включаем показ скрытых файлов и папок:
defaults write com.apple.Finder AppleShowAllFiles 1 && killall Finder

#### Выключаем показ скрытых файлов и папок:
defaults write com.apple.Finder AppleShowAllFiles 0 && killall Finder

[Источник](https://www.iguides.ru/forum/showthread.php?t=55120)

[Статья по форматированию приглашения bash](https://rtfm.co.ua/bash-nastraivaem-konsol-pod-sebya/)

[Статья по настройке цветов приглашения bash](https://wiki.archlinux.org/index.php/Color_Bash_Prompt_(%D0%A0%D1%83%D1%81%D1%81%D0%BA%D0%B8%D0%B9))

#### Настройка цветного приглашения(Зел\циан\розов):
open $HOME —> .bash_profile —> Вставить это:

```
PS1='\[\e[0;32m\]\u\[\e[m\] \[\e[0;36m\]\w\[\e[m\] \[\e[0;35m\]\$\[\e[m\] \[\e[0;37m\]'
[[ -s "$HOME/.profile" ]] && source "$HOME/.profile" # Load the default .profile

[[ -s "$HOME/.rvm/scripts/rvm" ]] && source "$HOME/.rvm/scripts/rvm" # Load RVM into a shell session *as a function*

```

Затем:
```
еxport PS1="[33[0;36m]u[33[m]@[33[32m]h:[33[33;1m]w[33[m]$ "
```

### Зел\циан\розов:

#### В папке HOME(открывается в терминале по умолчанию):
nano .bash_profile

#### Вставить и сохранить: 
```
PS1='\[\e[0;32m\]\u\[\e[m\] \[\e[0;36m\]\w\[\e[m\] \[\e[0;35m\]\$\[\e[m\] \[\e[0;37m\]'
```


# GIT:

* git checkout dev - переключиться на ветку dev
* git pull - запулиться (тянутся все изменения в проекте)
* git pull origin dev - запулиться с ветки dev
* git checkout -b new_branch - "ответвиться", создать от текущей ветки ветку с именем new_branch
* git commit -m «message» - коммит с сообщением message
* git push new_branch - запушить ветку dev в удаленный репозиторий
* git reset --hard HEAD - вернуться к последнему комету без сохранения текущих изменений
* git pull --all или  git fetch --all- подтягивает все ветки
* git branch -D <branchname> - удаление локальной ветки
* git push origin --delete <branchname> - удаление удаленной ветки(в удаленном репозитории)

Добавить готовый проект на гитхаб:
1. git init
2. git remote add origin git@github.com:Anton2501/react-new.git
3. сделать коммит
4. git pull origin master
5. git push -u origin master



# NPM
Структура версии пакета npm:
### [a.b.c]:
* a - структурные изменения(порядок аргументов функций, например)
* b - добавились новые возможности
* c - багофиксы


# HTML

```html
<picture>
  <source media="(min-width: 1200px)" srcset="img/logo-sedona-desktop.svg">
  <source media="(min-width: 768px)" srcset="img/logo-sedona-tablet.svg">
  <img src="img/logo-sedona-mobile.svg" alt="logo" class="logo__picture">
</picture>
```


# CSS

##### Вот так можно заимпортить CSS в SCSS:

```
@import "CSS:../../bower_components/normalize.css/normalize.css";
```

Left: 50%;
Top: 50%;
transform: translate3d(-50%, -50%, 0);


##### Псевдоклассы:

[Статья на то, что ниже](https://webcareer.ru/primery-ispolzovaniya-nth-child.html)

* Выбираем произвольный элемент:
```html
li:nth-child(3) {
	background: #4caf50;
}
```

* Выбираем четные элементы:
```html
li:nth-child(even) { /* или можно использовать формулу 2n */
	background: #4caf50;
}
```

* Выбираем нечетные элементы:
```html
li:nth-child(odd) { /* или можно использовать формулу 2n+1 */
	background: #4caf50;
}
```

* Выбираем каждый третий элемент:
```html
li:nth-child(3n) {
	background: #4caf50;
}
```

* Выбираем каждый третий элемент, начиная с первого:
```html
li:nth-child(3n+1) {
	background: #4caf50;
}
```

* Выбираем первые три элемента:
```html
li:nth-child(-n+3) {
	background: #4caf50;
}
```

* Выбираем все элементы начиная с пятого:
```html
li:nth-child(n+5) {
	background: #4caf50;
}
```


# Sublime Text 3:

**Добавить поддержку EMMET в JSX:**

Надо скачать плагин Babel + вставить код ниже в {Настройки - Preferences - Keybindings - User}:
```
[	
	{ "keys": ["alt+shift+f"], "command": "reindent" },
	{ "keys": ["tab"], "command": "expand_abbreviation_by_tab", "context": [
	        {
	            "operand": "source.js", 
	            "operator": "equal", 
	            "match_all": true, 
	            "key": "selector"
	        },
	        {   
	            "key": "selection_empty", 
	            "operator": "equal", 
	            "operand": true,
	            "match_all": true 
	        }	        
	    ]
	},
	{ "keys": ["tab"], "command": "next_field", "context":
	    [
	        { "key": "has_next_field", "operator": "equal", "operand": true }
	    ]
	}
]
```

[Источник](http://wesbos.com/emmet-react-jsx-sublime/)



#### Заменить табуляции на 2 пробела по умолчанию:
вставить код ниже в { Preferences - Settings - User }:

```
{
	"color_scheme": "Packages/Color Scheme - Default/Mariana.tmTheme",
	"ignored_packages":
	[
		"JavaScript Ultimate",
		"JavaScriptNext - ES6 Syntax",
		"JSX",
		"Numix Theme",
		"SideBarEnhancements",
		"Theme - Monokai Pro",
		"Vintage"
	],	
	"tab_size": 2,
	"translate_tabs_to_spaces": true
}
```

# VS Code:

**Плагины:**

* ESLint
* GitBlame
* Material icon theme PathIntelliense
* Prettier
* RainbowBrackets