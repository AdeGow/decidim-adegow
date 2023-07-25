# decidim-webpacker-issues
Track intents to fix webpacker compilation issues on decidim-application
Succesfully created decidim_application
Successfully created and migrated DB through rails db:drop db:create db:migrate
Potential issue running db:seed 
Message on Terminal is 
  Creating seeds for decidim-core...
  Creating seeds for decidim-system...
  rails aborted!
  NoMethodError: undefined method `allow_public_access=' for #<Decidim::StaticPage id: nil, title: {"ca"=>"Títol predeterminat per terms-and-conditions", "cs"=>"Výchozí název pro terms-and-conditions", "de"=>"Standardtitel für terms-and-conditions", "en"=>"Default title for terms-and-conditions", "es"=>"Título predeterminado para terms-and-conditions", "eu"=>"Izenburu lehenetsia orri honetarako: terms-and-conditions", "fi"=>"Oletusotsikko sivulle terms-and-conditions", "fr"=>"Titre par défaut pour terms-and-conditions", "it"=>"Titolo predefinito per terms-and-conditions", "ja"=>"terms-and-conditions のデフォルトのタイトル", "nl"=>"Standaard titel voor terms-and-conditions", "pl"=>"Domyślny tytuł dla terms-and-conditions", "pt"=>"Título padrão para terms-and-conditions", "ro"=>"Titlul implicit pentru terms-and-conditions"}, slug: "terms-and-conditions", content: {"ca"=>"Si us plau, afegeix contingut significatiu a la pàgina estàtica de terms-and-conditions dins el panell d'administració.", "cs"=>"Přidejte smysluplný obsah na statickou stránku terms-and-conditions na ovládacím panelu administrátora.", "de"=>"Fügen Sie der statischen Seite terms-and-conditions im Admin-Dashboard sinnvollen Inhalt hinzu.", "en"=>"Please add meaningful content to the terms-and-conditions static page on the admin dashboard.", "es"=>"Por favor, agrega contenido significativo a la página estática de terms-and-conditions en el panel de administración.", "eu"=>"Gehitu eduki adierazgarria terms-and-conditions (a)ren orri estatikoaren administrazio-panelean.", "fi"=>"Lisää merkityksellistä sisältöä staattiselle sivulle terms-and-conditions hallintapaneelista.", "fr"=>"Ajoutez un contenu pertinent à la page terms-and-conditions en allant sur l'interface d'administration.", "it"=>"Si prega di aggiungere contenuto significativo alla pagina statica terms-and-conditions il pannello di amministrazione.", "ja"=>"管理ダッシュボードの terms-and-conditions 静的ページに意味のあるコンテンツを追加してください。", "nl"=>"Voeg relevante inhoud aan het statische pagina van terms-and-conditions op het admin dashboard.", "pl"=>"Proszę dodać istotne treści do strony statycznej terms-and-conditions w panelu administratora.", "pt"=>"Por favor adicione conteúdo relevante à página estática terms-and-conditions no painel de administrador.", "ro"=>"Vă rugăm să adăugaţi conţinut semnificativ paginii statice terms-and-conditions de pe tabloul de bord al administratorului."}, decidim_organization_id: 1, created_at: nil, updated_at: nil, weight: nil, show_in_footer: true>
  /Users/adelinedegaulejac/code/AdeGow/decidim-personal-project/decidim_application/db/seeds.rb:9:in `<main>'
  /Users/adelinedegaulejac/code/AdeGow/decidim-personal-project/decidim_application/bin/rails:5:in `<top (required)>'
  /Users/adelinedegaulejac/code/AdeGow/decidim-personal-project/decidim_application/bin/spring:10:in `block in <top (required)>'
  /Users/adelinedegaulejac/code/AdeGow/decidim-personal-project/decidim_application/bin/spring:7:in `<top (required)>'
  Tasks: TOP => db:seed
  (See full trace by running task with --trace)

Issue after running rails s

  ➜  decidim_application git:(master) rails s
    => Booting Puma
    => Rails 6.1.6 application starting in development 
    => Run `bin/rails server --help` for more startup options
    Puma starting in single mode...
    * Puma version: 5.6.4 (ruby 3.1.2-p20) ("Birdie's Version")
    *  Min threads: 5
    *  Max threads: 5
    *  Environment: development
    *          PID: 47475
    * Listening on http://127.0.0.1:3000
    * Listening on http://[::1]:3000
    Use Ctrl-C to stop

    Started GET "/" for ::1 at 2023-07-25 20:37:31 +0200
   (0.8ms)  SELECT "schema_migrations"."version" FROM "schema_migrations" ORDER BY "schema_migrations"."version" ASC
    Decidim::Organization Load (1.6ms)  SELECT "decidim_organizations".* FROM "decidim_organizations" WHERE "decidim_organizations"."host" = $1 LIMIT $2  [["host", "localhost"], ["LIMIT", 1]]
  Processing by Decidim::HomepageController#show as HTML
  [Webpacker] Compiling...
  [Webpacker] Compilation failed:
  /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych/visitors/to_ruby.rb:430:in `visit_Psych_Nodes_Alias': Unknown alias: default (Psych::BadAlias)
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych/visitors/visitor.rb:30:in `visit'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych/visitors/visitor.rb:6:in `accept'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych/visitors/to_ruby.rb:35:in `accept'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych/visitors/to_ruby.rb:345:in `block in revive_hash'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych/visitors/to_ruby.rb:343:in `each'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych/visitors/to_ruby.rb:343:in `each_slice'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych/visitors/to_ruby.rb:343:in `revive_hash'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych/visitors/to_ruby.rb:167:in `visit_Psych_Nodes_Mapping'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych/visitors/visitor.rb:30:in `visit'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych/visitors/visitor.rb:6:in `accept'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych/visitors/to_ruby.rb:35:in `accept'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych/visitors/to_ruby.rb:345:in `block in revive_hash'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych/visitors/to_ruby.rb:343:in `each'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych/visitors/to_ruby.rb:343:in `each_slice'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych/visitors/to_ruby.rb:343:in `revive_hash'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych/visitors/to_ruby.rb:167:in `visit_Psych_Nodes_Mapping'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych/visitors/visitor.rb:30:in `visit'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych/visitors/visitor.rb:6:in `accept'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych/visitors/to_ruby.rb:35:in `accept'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych/visitors/to_ruby.rb:318:in `visit_Psych_Nodes_Document'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych/visitors/visitor.rb:30:in `visit'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych/visitors/visitor.rb:6:in `accept'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych/visitors/to_ruby.rb:35:in `accept'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych.rb:335:in `safe_load'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych.rb:370:in `load'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych.rb:671:in `block in load_file'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych.rb:670:in `open'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/3.1.0/psych.rb:670:in `load_file'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/gems/3.1.0/gems/decidim-core-0.27.3/lib/decidim/webpacker/configuration.rb:23:in `configuration_file'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/gems/3.1.0/gems/decidim-core-0.27.3/lib/decidim/webpacker/runner.rb:20:in `decidim_initialize'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/gems/3.1.0/gems/decidim-core-0.27.3/lib/decidim/webpacker/runner.rb:12:in `block in included'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/gems/3.1.0/gems/webpacker-6.0.0.rc.5/lib/webpacker/runner.rb:6:in `new'
  	from /Users/adelinedegaulejac/.rbenv/versions/3.1.2/lib/ruby/gems/3.1.0/gems/webpacker-6.0.0.rc.5/lib/webpacker/runner.rb:6:in `run'
  	from ./bin/webpack:20:in `block in <main>'
  	from ./bin/webpack:19:in `chdir'
  	from ./bin/webpack:19:in `<main>'
  
  Completed 500 Internal Server Error in 949ms (ActiveRecord: 0.0ms | Allocations: 27119)
  
  
    
  Webpacker::Manifest::MissingEntryError (Webpacker can't find decidim_dev.css in /Users/adelinedegaulejac/code/AdeGow/decidim-personal-project/decidim_application/public/decidim-packs/manifest.json. Possible causes:
  1. You want to set webpacker.yml value of compile to true for your environment
     unless you are using the `webpack -w` or the webpack-dev-server.
  2. webpack has not yet re-run to reflect updates.
  3. You have misconfigured Webpacker's config/webpacker.yml file.
  4. Your webpack configuration is not creating a manifest.
  Your manifest contains:
  {
  }
  ):
    
  webpacker (6.0.0.rc.5) lib/webpacker/manifest.rb:79:in `handle_missing_entry'
  webpacker (6.0.0.rc.5) lib/webpacker/manifest.rb:32:in `lookup_pack_with_chunks!'
  webpacker (6.0.0.rc.5) lib/webpacker/helper.rb:152:in `block in sources_from_manifest_entrypoints'
  webpacker (6.0.0.rc.5) lib/webpacker/helper.rb:152:in `map'
  webpacker (6.0.0.rc.5) lib/webpacker/helper.rb:152:in `sources_from_manifest_entrypoints'
  webpacker (6.0.0.rc.5) lib/webpacker/helper.rb:146:in `stylesheet_pack_tag'
  decidim-dev (0.27.3) app/controllers/concerns/decidim/dev/needs_development_tools.rb:20:in `apply_development_tools'
  activesupport (6.1.6) lib/active_support/callbacks.rb:427:in `block in make_lambda'
  activesupport (6.1.6) lib/active_support/callbacks.rb:198:in `block (2 levels) in halting'
  actionpack (6.1.6) lib/abstract_controller/callbacks.rb:34:in `block (2 levels) in <module:Callbacks>'
  activesupport (6.1.6) lib/active_support/callbacks.rb:199:in `block in halting'
  activesupport (6.1.6) lib/active_support/callbacks.rb:512:in `block in invoke_before'
  activesupport (6.1.6) lib/active_support/callbacks.rb:512:in `each'
  activesupport (6.1.6) lib/active_support/callbacks.rb:512:in `invoke_before'
  activesupport (6.1.6) lib/active_support/callbacks.rb:115:in `block in run_callbacks'
  activesupport (6.1.6) lib/active_support/callbacks.rb:137:in `run_callbacks'
  actionpack (6.1.6) lib/abstract_controller/callbacks.rb:41:in `process_action'
  actionpack (6.1.6) lib/action_controller/metal/rescue.rb:22:in `process_action'
  actionpack (6.1.6) lib/action_controller/metal/instrumentation.rb:34:in `block in process_action'
  activesupport (6.1.6) lib/active_support/notifications.rb:203:in `block in instrument'
  activesupport (6.1.6) lib/active_support/notifications/instrumenter.rb:24:in `instrument'
  activesupport (6.1.6) lib/active_support/notifications.rb:203:in `instrument'
  actionpack (6.1.6) lib/action_controller/metal/instrumentation.rb:33:in `process_action'
  actionpack (6.1.6) lib/action_controller/metal/params_wrapper.rb:249:in `process_action'
  activerecord (6.1.6) lib/active_record/railties/controller_runtime.rb:27:in `process_action'
  actionpack (6.1.6) lib/abstract_controller/base.rb:165:in `process'
  actionview (6.1.6) lib/action_view/rendering.rb:39:in `process'
  actionpack (6.1.6) lib/action_controller/metal.rb:190:in `dispatch'
  actionpack (6.1.6) lib/action_controller/metal.rb:254:in `dispatch'
  actionpack (6.1.6) lib/action_dispatch/routing/route_set.rb:50:in `dispatch'
  actionpack (6.1.6) lib/action_dispatch/routing/route_set.rb:33:in `serve'
  actionpack (6.1.6) lib/action_dispatch/journey/router.rb:50:in `block in serve'
  actionpack (6.1.6) lib/action_dispatch/journey/router.rb:32:in `each'
  actionpack (6.1.6) lib/action_dispatch/journey/router.rb:32:in `serve'
  actionpack (6.1.6) lib/action_dispatch/routing/route_set.rb:842:in `call'
  railties (6.1.6) lib/rails/engine.rb:539:in `call'
  railties (6.1.6) lib/rails/railtie.rb:207:in `public_send'
  railties (6.1.6) lib/rails/railtie.rb:207:in `method_missing'
  actionpack (6.1.6) lib/action_dispatch/routing/mapper.rb:20:in `block in <class:Constraints>'
  actionpack (6.1.6) lib/action_dispatch/routing/mapper.rb:49:in `serve'
  actionpack (6.1.6) lib/action_dispatch/journey/router.rb:50:in `block in serve'
  actionpack (6.1.6) lib/action_dispatch/journey/router.rb:32:in `each'
  actionpack (6.1.6) lib/action_dispatch/journey/router.rb:32:in `serve'
  actionpack (6.1.6) lib/action_dispatch/routing/route_set.rb:842:in `call'
  batch-loader (1.5.0) lib/batch_loader/middleware.rb:11:in `call'
  omniauth (2.1.1) lib/omniauth/strategy.rb:202:in `call!'
  omniauth (2.1.1) lib/omniauth/strategy.rb:169:in `call'
  omniauth (2.1.1) lib/omniauth/builder.rb:44:in `call'
  warden (1.2.9) lib/warden/manager.rb:36:in `block in call'
  warden (1.2.9) lib/warden/manager.rb:34:in `catch'
  warden (1.2.9) lib/warden/manager.rb:34:in `call'
  decidim-core (0.27.3) lib/decidim/middleware/strip_x_forwarded_host.rb:12:in `call'
  decidim-core (0.27.3) lib/decidim/middleware/current_organization.rb:22:in `call'
  rack (2.2.3.1) lib/rack/tempfile_reaper.rb:15:in `call'
  rack (2.2.3.1) lib/rack/etag.rb:27:in `call'
  rack (2.2.3.1) lib/rack/conditional_get.rb:27:in `call'
  rack (2.2.3.1) lib/rack/head.rb:12:in `call'
  actionpack (6.1.6) lib/action_dispatch/http/permissions_policy.rb:22:in `call'
  actionpack (6.1.6) lib/action_dispatch/http/content_security_policy.rb:19:in `call'
  rack (2.2.3.1) lib/rack/session/abstract/id.rb:266:in `context'
  rack (2.2.3.1) lib/rack/session/abstract/id.rb:260:in `call'
  actionpack (6.1.6) lib/action_dispatch/middleware/cookies.rb:689:in `call'
  activerecord (6.1.6) lib/active_record/migration.rb:601:in `call'
  actionpack (6.1.6) lib/action_dispatch/middleware/callbacks.rb:27:in `block in call'
  activesupport (6.1.6) lib/active_support/callbacks.rb:98:in `run_callbacks'
  actionpack (6.1.6) lib/action_dispatch/middleware/callbacks.rb:26:in `call'
  actionpack (6.1.6) lib/action_dispatch/middleware/executor.rb:14:in `call'
  actionpack (6.1.6) lib/action_dispatch/middleware/actionable_exceptions.rb:18:in `call'
  actionpack (6.1.6) lib/action_dispatch/middleware/debug_exceptions.rb:29:in `call'
  web-console (4.2.0) lib/web_console/middleware.rb:132:in `call_app'
  web-console (4.2.0) lib/web_console/middleware.rb:28:in `block in call'
  web-console (4.2.0) lib/web_console/middleware.rb:17:in `catch'
  web-console (4.2.0) lib/web_console/middleware.rb:17:in `call'
  actionpack (6.1.6) lib/action_dispatch/middleware/show_exceptions.rb:33:in `call'
  railties (6.1.6) lib/rails/rack/logger.rb:37:in `call_app'
  railties (6.1.6) lib/rails/rack/logger.rb:26:in `block in call'
  activesupport (6.1.6) lib/active_support/tagged_logging.rb:99:in `block in tagged'
  activesupport (6.1.6) lib/active_support/tagged_logging.rb:37:in `tagged'
  activesupport (6.1.6) lib/active_support/tagged_logging.rb:99:in `tagged'
  railties (6.1.6) lib/rails/rack/logger.rb:26:in `call'
  actionpack (6.1.6) lib/action_dispatch/middleware/remote_ip.rb:81:in `call'
  request_store (1.5.1) lib/request_store/middleware.rb:19:in `call'
  actionpack (6.1.6) lib/action_dispatch/middleware/request_id.rb:26:in `call'
  rack (2.2.3.1) lib/rack/method_override.rb:24:in `call'
  activesupport (6.1.6) lib/active_support/cache/strategy/local_cache_middleware.rb:29:in `call'
  actionpack (6.1.6) lib/action_dispatch/middleware/executor.rb:14:in `call'
  actionpack (6.1.6) lib/action_dispatch/middleware/static.rb:24:in `call'
  rack (2.2.3.1) lib/rack/sendfile.rb:110:in `call'
  actionpack (6.1.6) lib/action_dispatch/middleware/host_authorization.rb:148:in `call'
  webpacker (6.0.0.rc.5) lib/webpacker/dev_server_proxy.rb:25:in `perform_request'
  rack-proxy (0.7.6) lib/rack/proxy.rb:87:in `call'
  rack-cors (1.1.1) lib/rack/cors.rb:100:in `call'
  railties (6.1.6) lib/rails/engine.rb:539:in `call'
  puma (5.6.4) lib/puma/configuration.rb:252:in `call'
  puma (5.6.4) lib/puma/request.rb:77:in `block in handle_request'
  puma (5.6.4) lib/puma/thread_pool.rb:340:in `with_force_shutdown'
  puma (5.6.4) lib/puma/request.rb:76:in `handle_request'
  puma (5.6.4) lib/puma/server.rb:441:in `process_client'
  puma (5.6.4) lib/puma/thread_pool.rb:147:in `block in spawn_thread'



