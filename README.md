go-ide
===

![Neovim Gopher](https://raw.githubusercontent.com/plentiform/go-ide/master/gopher.png)

## Описание

Это проект, [Neovim](https://neovim.io/) интегрированной среды разработки (IDE) из неовима для [Golang](https://golang.org/). Первоначальный автор сделал обвязку сборки неовима для работы на десктопах, я же ставлю для себя целью эту сборку адаптировать для работы на сервере, с подключением через любой терминал. Основная моя цель - поддержка разработки на iPad (в качестве эксперимента - можно ли отказаться от ноутбуков или мир еще не готов), но в принципе эта штука будет работать с любым терминалом в любой среде.

## Предварительные требования

1. Установите golang: https://golang.org/doc/install
2. Добавьте переменные окружения в `~/.bashrc` (здесь и далее мы рассматриваем bash как командную оболочку и в качестве серверной части Ubuntu, но любой линукс с любым шелом так или иначе подойдет):
```
export GOPATH=$HOME/go
export PATH=$GOPATH/bin:/usr/local/go/bin:$PATH
```
(не забудьте засорсить изменения в текущую сессию терминала `source ~/.bashrc` или откройте новую сессию терминала, я частенько забываю это делать)

2. Поставьте gocode: `go get -u github.com/stamblerre/gocode`
3. Установите поддержку питона для neovim: `pip3 install pynvim`
4. Поставьте neovim: https://github.com/neovim/neovim/wiki/Installing-Neovim
5. Поставьте vim-plug: https://github.com/junegunn/vim-plug#installation

## Установка

1. Обязательно убедитесь что все предварительные требования соответствуют, а то не взлетит ^
2. Сделайте папочку для конфига, если ее еще нет: `mkdir -p ~/.config/nvim`
2. Скачайте [конфиг](https://raw.githubusercontent.com/kodji/go-ide/master/init.vim): 
```
cd ~/.config/nvim; wget https://raw.githubusercontent.com/kodji/go-ide/master/init.vim
```
5. Откройте конфигурацию: `nvim ~/.config/nvim/init.vim`
6. По идее при открытии конфигурации все должно само завертеться, если нет - нажмите `:` потом `PlugInstall` <kbd>Enter</kbd>
7. Поставьте бинари vim-go нажмите `:` наберите `GoInstallBinaries` <kbd>Enter</kbd>

## Фишки

- Браузер файлов: `nt` - открыть\закрыть, m - открыть меню действий с папкой\файлом на котором курсор в дереве

![](gifs/nerdtree.gif)

- Поиск по файловой системе: <kbd>Ctrl</kbd>-`p`

![](gifs/fzf.gif)

- Поиск по текущему файлу: `/` (классический вимовский - ввести поисковую фразу, нажать <kbd>Enter</kbd>, следующее вхождение `n`, предыдущее `N`, очистить подсветку <kbd>Ctrl</kbd>-`l`)

![](gifs/text_search.gif)

- Перейти к определению метода под курсором: `gd` (вернуться обратно <kbd>Ctrl</kbd>-`o`)

![](gifs/go_def.gif)

- Подсказка по методам (двигаться по списку подсказок вниз: <kbd>Tab</kbd>, вверх <kbd>Shift</kbd>-<kbd>Tab</kbd>, выбрать <kbd>Enter</kbd>)

![](gifs/ncm2.gif)

- Сниппеты / шорткаты (следующая <kbd>Ctrl</kbd>-`j`, предыдущая <kbd>Ctrl</kbd>-`k`)

![](gifs/snippets.gif)

- Дебаггер

![](gifs/debugger.gif)

- Автоимпорты и автоформатирование кода

![](gifs/imports.gif)
