Stats about the project

`rake stats`

Solution for `Can't verify CSRF token authenticity`

```ruby
class ApplicationController < ActionController::Base
  protect_from_forgery with: :null_session, if: Proc.new { |c| c.request.format == 'application/json' }
end
```
