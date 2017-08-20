# purescript-facebook
Idiomatic Purescript bindings for the Facebook SDK

### Disclaimer: this project is a work in progress

Init Facebook SDK & retrieve a current login status:

``` purescript
import Control.Monad.Aff (Aff)
import Control.Monad.Aff.Console (logShow)
import Control.Monad.Eff.Console (CONSOLE)
import Facebook.Sdk (Config(Config), init, loginStatus) as FB

initFacebook :: ∀ e. Aff (console :: CONSOLE | e) Unit
initFacebook = do
  sdk <- FB.init $ defaultConfig "1234567890" -- your app id
  info <- FB.loginStatus sdk
  logShow info
```

Outputs to the console:
```
Facebook.Sdk.FbStatusInfo {authResponse: Data.Maybe.Nothing, status: Facebook.Sdk.NotAuthorized}
```
