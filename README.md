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
