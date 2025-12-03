# Как Масштабировать Вашу Модель

> **📖 Любительский перевод**  
> Это неофициальный русский перевод. Оригинал на английском: https://jax-ml.github.io/scaling-book
>
> Если вы заметили ошибку в переводе, пожалуйста, не напрягайте оригинальных авторов (скорее всего это я ошибся), и оставьте issue здесь: https://github.com/KineticCookie/scaling-book/issues

В этой книге мы разбираемся с тем, как масштабировать большие языковые модели на TPU. Вы узнаете, как устроены TPU, как LLM работают на больших масштабах, и как правильно выбирать стратегии параллелизма для обучения и инференса, чтобы избежать узких мест.

### Благодарности

Авторы книги — Jacob Austin, Sholto Douglas, Roy Frostig, Anselm Levskaya, Charlie Chen, Sharad Vikram, Federico Lebron, Peter Choy, Vinay Ramasesh и Albert Webson из Google DeepMind. Многие идеи впервые сформулировали James Bradbury и Reiner Pope.

Сайт построен на Jekyll-теме в стиле Distill от https://github.com/alshedivat/al-folio и команды Distill. Спасибо!

### Локальная сборка

Для сборки понадобятся Ruby, ImageMagick и Jupyter. На MacOS ставятся через Homebrew:

```
brew install imagemagick ruby
pip install jupyter
```

Проверьте, что используется правильная версия Ruby (минимум 3.4.5). Возможно, придется добавить в `.bashrc`:

```
if [ -d "/opt/homebrew/opt/ruby/bin" ]; then
  export PATH=/opt/homebrew/opt/ruby/bin:$PATH
  export PATH=`gem environment gemdir`/bin:$PATH
fi
```

Теперь можно клонировать и запустить:

```
git clone https://github.com/jax-ml/scaling-book.git
cd scaling-book
bundle install
bundle exec jekyll serve
```

Книга откроется по адресу `http://127.0.0.1:4000/scaling-book`.

Для деплоя на GitHub Pages (нужны права на запись) выполните `sh bin/deploy` — займет минуты 3.

### Как помочь

Нашли ошибку или есть вопрос? Оставьте комментарий на сайте (через Giscus) или в обсуждениях на GitHub. PR тоже приветствуются! Можно также написать на jaaustin [at] google [dot] com.

Для контрибуций на GitHub нужно подписать Google CLA (Contributor License Agreement): https://cla.developers.google.com/clas.

> CLA требуется только для оригинального репозитория https://github.com/jax-ml/scaling-book
>
> Так как это неофициальный форк с переводом, CLA здесь не нужен.


### Цитирование

Для академических ссылок используйте:

```Austin et al., "How to Scale Your Model", Google DeepMind, online, 2025.```

BibTeX:

```
@article{scaling-book,
  title = {How to Scale Your Model},
  author = {Austin, Jacob and Douglas, Sholto and Frostig, Roy and Levskaya, Anselm and Chen, Charlie and Vikram, Sharad and Lebron, Federico and Choy, Peter and Ramasesh, Vinay and Webson, Albert and Pope, Reiner},
  publisher = {Google DeepMind},
  howpublished = {Online},
  note = {Retrieved from https://jax-ml.github.io/scaling-book/},
  year = {2025}
}
```

![dragon](assets/img/dragon.png)

*Книга изначально называлась "How To Scale Your Dragon" (отсылка к мультфильму Dreamworks) — отсюда драконы.*
