# Muhammad-ijazCRT-hostinger-link-storage-outside-of-codeuse Illuminate\Support\Facades\Artisan;


    use Illuminate\Support\Facades\File;
    
    Route::get('/fix-storage-link', function () {
    
        // Path where the link SHOULD be created (public_html/storage)
        $publicStoragePath = base_path('../storage');
    
        // Actual storage/app/public path
        $storagePath = storage_path('app/public');
    
        // Delete existing link if exists
        if (is_link($publicStoragePath) || file_exists($publicStoragePath)) {
            File::delete($publicStoragePath);
        }
    
        // Create symlink
        symlink($storagePath, $publicStoragePath);
    
        return "Storage link created successfully!";
    });




# crossmint sandbox

    Crossmint WooCommerce Payment Settings
    ======================================
    
    Copy these values into:
    WooCommerce → Settings → Payments → Crossmint
    
    WARNING: This file contains API keys. Do not commit it to a public repository
    or share it outside your team.
    
    --------------------------------------
    General
    --------------------------------------
    Enabled:                 yes
    Title:                   Crossmint
    Description:             Pay securely with card or crypto via Crossmint.
    Sandbox mode:            yes
    API base URL:            https://staging.crossmint.com/api
    Debug / logging:         no
    Timeout:                 30
    Locale:                  en-US
    
    --------------------------------------
    API keys
    --------------------------------------
    Server API key:
    sk_staging_A5uXQeoqfMnuf7QgX9usWWwDLApuJop4yiMzBxgnrMw1QBv5HtjGwdo9vXZ4j8gJtwuhgGx5gWJ7MctbWM18jBLSoxPmHJtJ44aQEirm283z4962F5hPzuUatdZpxqSgZTQsJH5uQ1Z5nR1yQjETPWd2SXE28MNpG7mXadCgn1V5GVrj8xybTrP839GcN8Duvo4NmzsMxv2rE9n5BXmp3wa3
    
    Client API key:
    ck_staging_A5uXQeoqfMnuf7QgX9usWWwDLApuJop4yiMzBxgnrMw1QBv5HtikFLCHZLLHLcNCxmvNbK4kEeAQgGAeLmN9EQfFDuwJrFdZVZYp2HwwUSkVshtFVvLWaZVQ7ECvADYN4GLUFS3YhuzgiS1Yiux8jAkdR1sZkH8QqKB1Zue1UNKDYXsd5UVXVeNCYywfd3jeAE3CTfBJR9TtVK1uJ4NUCQQi
    
    Webhook secret:          (empty)
    
    --------------------------------------
    Project / collection
    --------------------------------------
    Project ID:              daa018b7-000d-4c3c-9e97-7b232d172a5d
    Collection ID:           b4143f4e-cba7-4814-9715-57c58546146f
    Checkout mode:           solana_token
    Chain:                   sol
    Currency:                usd
    Mint hash:               7EivYFyNfgGj8xbUymR7J4LuxUHLKRzpLaERHLvi7Dgu
    Solana wallet address:   23V1yitu4DaTQGSDJPTTRvoECdVsbdwkUPmKqR48ssc6
    Show wallet field:       no
    Max slippage (bps):      500
    
    --------------------------------------
    Webhook URL (update domain per site)
    --------------------------------------
    Local example:
    http://localhost/word/?wc-api=wc_gateway_crossmint&action=webhook
    
    Other site example:
    https://YOUR-DOMAIN.com/?wc-api=wc_gateway_crossmint&action=webhook
    
    --------------------------------------
    Staging test card
    --------------------------------------
    Card number:  4000 0200 0000 0000
    Use any future expiry and any 3-digit CVC in sandbox.
