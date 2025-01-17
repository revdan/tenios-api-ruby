# Tenios API Client ☎️

HTTP client for [Tenios API].

[Tenios API]: https://www.tenios.de/doc-topic/voice-api

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'tenios-api'
```

## Usage

```ruby
require 'tenios-api'

client = Tenios::API::Client.new(access_key: ENV['TENIOS_ACCESS_KEY'])
```

### Call Detail Records

[Tenios documentation](https://www.tenios.de/en/doc/api-cdr-request)

```ruby
client.cdrs.retrieve(Time.utc(2019, 2, 1)..Time.utc(2019, 2, 2))
# returns lazy Enumerator with the records
```

### Number Order

[Tenios documentation](https://www.tenios.de/en/doc/api-number-order)

```ruby
# check Tenios documentation for verification options
verification_id = client.verification.create(options)['verification_id']
order_id = client.number.order(verification_id: verification_id)['order_id']
```

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/carwow/tenios-api-ruby.

## License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).
