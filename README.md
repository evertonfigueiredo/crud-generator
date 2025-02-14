![Laravel Crud Generator](https://banners.beyondco.de/Laravel%20CRUD.png?theme=dark&packageManager=composer+require&packageName=ibex%2Fcrud-generator&pattern=architect&style=style_1&description=Laravel+CRUD+Generator&md=1&showWatermark=0&fontSize=100px&images=gift)

![Packagist](https://img.shields.io/badge/Packagist-v2-green.svg?style=flat-square)
![Licence](https://img.shields.io/badge/Licence-MIT-green.svg?style=flat-square)
![StyleCI](https://img.shields.io/badge/StyleCI-pass-green.svg?style=flat-square)

Este pacote **Laravel CRUD Generator v2.x** gera automaticamente **Controllers**, **Models** (com relações Eloquent) e **Views** em **Bootstrap** ou **Tailwind CSS** para o desenvolvimento de suas aplicações com um único comando. A nova versão `v2.x` oferece opções de stack como `bootstrap`, `tailwind`, `livewire` (as views do Livewire serão geradas em **Tailwind CSS**) e `API` apenas.

- Cria **Models** com relações Eloquent.
- Cria **Controllers** com todos os recursos.
- Cria **API Controllers** com todas as requisições.
- Cria **Components** com todos os recursos para Livewire.
- Cria **views** em Bootstrap ou Tailwind.

Este é o melhor gerador de CRUD para projetos Laravel, mesmo em instalações em branco. Ele instala automaticamente o starter kit [laravel/breeze](https://github.com/laravel/breeze) ou [laravel/ui](https://github.com/laravel/ui) (para Bootstrap 5) em instalações novas do Laravel.

## Requisitos
- Laravel >= 10.x
- PHP >= 8.1

## Instalação
1 - Instale o pacote:
```
composer require evertonfigueiredo/crud-generator --dev
```
2 - Publique a configuração padrão do pacote (opcional):
```
php artisan vendor:publish --tag=crud
```

**Para versões mais antigas do Laravel (<10.x), use a [v1.x](https://github.com/awais-vteams/laravel-crud-generator/tree/v1.6):**
```
composer require evertonfigueiredo/crud-generator:1.6 --dev
```

## Uso
```
php artisan make:crud {nome_da_tabela}

php artisan make:crud bancos
```

Adicione uma rota no `web.php`:
```
Route::resource('bancos', BancoController::class);
```

Para `Livewire`, adicione as rotas abaixo:
```
Route::get('/bancos', \App\Livewire\Bancos\Index::class)->name('bancos.index');
Route::get('/bancos/create', \App\Livewire\Bancos\Create::class)->name('bancos.create');
Route::get('/bancos/show/{banco}', \App\Livewire\Bancos\Show::class)->name('bancos.show');
Route::get('/bancos/update/{banco}', \App\Livewire\Bancos\'::class)->name('bancos.edit');
```

Para `api`, adicione as rotas abaixo:
```
Route::apiResource('bancos', BancoController::class);
```

O nome da rota deve estar no plural e em formato slug.

#### Opções
- Tech Stack

  <img width="535" alt="image" src="https://github.com/awais-vteams/laravel-crud-generator/assets/10154558/c1e2e2a6-7fcd-4c4a-a393-56d8fe6eb231">
```
php artisan make:crud {nome_da_tabela} {bootstrap,tailwind,livewire,api}

php artisan make:crud bancos bootstrap  //Isso criará views em Bootstrap 5 usando Blade
php artisan make:crud bancos tailwind   //Isso criará views em Tailwind CSS usando Blade
php artisan make:crud bancos livewire   //Isso criará views em Tailwind CSS com componentes Livewire
php artisan make:crud bancos api        //Isso criará apenas controllers para API
```
- Rota personalizada:
```
php artisan make:crud {nome_da_tabela} --route={nome_da_rota}
```

## Exemplos

*Model*
<img width="100%" alt="image" src="https://github.com/awais-vteams/laravel-crud-generator/assets/10154558/6b3c3dc1-a983-4893-a45c-94dbb8da50fc">

*Controller*
<img width="100%" alt="image" src="https://github.com/awais-vteams/laravel-crud-generator/assets/10154558/6a7948ed-90b7-46f9-a8b3-abb56fe0fb71">

*Componente Livewire*
<img width="100%" alt="image" src="https://github.com/awais-vteams/laravel-crud-generator/assets/10154558/e4c3bca5-f27a-41a8-a5bd-00c51b156235">

*Controller apenas para API*

<img width="500" alt="image" src="https://github.com/awais-vteams/laravel-crud-generator/assets/10154558/a42329a8-58e7-49ef-8e21-b6227555542b">

*Tailwind CSS*
<img width="100%" alt="image" src="https://github.com/awais-vteams/laravel-crud-generator/assets/10154558/b5ca686a-5a3b-4c60-849c-e757d16dc1a0">

*Bootstrap*
![Listing](https://i.imgur.com/UH5XGuw.png)

*Formulário em Tailwind*

<img width="756" alt="image" src="https://github.com/awais-vteams/laravel-crud-generator/assets/10154558/b7d437ac-5d2b-4673-80ab-c2f7eb88e835">

*Formulário em Bootstrap*
![Form](https://i.imgur.com/poRiZRO.png)

## Personalização  
Você pode personalizar 100% das views geradas. Para isso, siga os passos abaixo:    

- Execute o comando `php artisan vendor:publish --tag=crud`. Isso criará o arquivo `crud.php` na pasta `config/`.
- Atualize a variável `stub_path` para apontar para sua própria pasta de stubs, por exemplo: `'stub_path' => resource_path('stubs/'),`.  
- Copie os arquivos de stubs do pacote:
```
php artisan vendor:publish --tag=stubs-crud
```
- Faça suas alterações nos arquivos de stubs. (Você pode excluir arquivos ou pastas extras se não for usá-los).  
- Execute o comando para gerar o CRUD e você obterá as views atualizadas.  

---

## Modificações para Português (pt-br)
Estou modificando esta biblioteca para gerar CRUDs em português (pt-br). As views, mensagens e estruturas estarão adaptadas para o idioma português do Brasil, facilitando o desenvolvimento de aplicações para o mercado brasileiro.

---

## Autor

M Awais // [Envie um e-mail](mailto:asargodha@gmail.com)

Contrate-me no [LinkedIn](https://www.linkedin.com/in/asargodha/)

### Tradutor

Everton  Figueiredo// [Envie um e-mail](mailto:contato@evertonfigueiredo.com.br)

Contrate-me no [LinkedIn](https://www.linkedin.com/in/everton-figueiredo/)

---

Se precisar de mais ajustes ou detalhes, é só avisar! 😊