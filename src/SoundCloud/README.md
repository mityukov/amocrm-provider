# SoundCloud

```bash
composer require socialiteproviders/soundcloud
```

## Installation & Basic Usage

Please see the [Base Installation Guide](https://socialiteproviders.com/usage/), then follow the provider specific instructions below.

### Add configuration to `config/services.php`

```php
'soundcloud' => [    
  'client_id' => env('SOUNDCLOUD_CLIENT_ID'),  
  'client_secret' => env('SOUNDCLOUD_CLIENT_SECRET'),  
  'redirect' => env('SOUNDCLOUD_REDIRECT_URI') 
],
```

### Add provider event listener

Configure the package's listener to listen for `SocialiteWasCalled` events.

Add the event to your `listen[]` array in `app/Providers/EventServiceProvider`. See the [Base Installation Guide](https://socialiteproviders.com/usage/) for detailed instructions.

```php
protected $listen = [
    \SocialiteProviders\Manager\SocialiteWasCalled::class => [
        // ... other providers
        'SocialiteProviders\\SoundCloud\\SoundCloudExtendSocialite@handle',
    ],
];
```

### Usage

You should now be able to use the provider like you would regularly use Socialite (assuming you have the facade installed):

```php
return Socialite::with('soundcloud')->redirect();
```

### Returned User fields

- ``id``
- ``nickname``
- ``avatar``