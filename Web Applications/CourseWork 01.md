### Entity Relationship Diagram
![[Screenshot 2023-03-05 at 5.46.27 PM.png]]

### Models

##### User
```PHP
<?php

namespace App\Models;

// use Illuminate\Contracts\Auth\MustVerifyEmail;
use Illuminate\Database\Eloquent\Factories\HasFactory;
use Illuminate\Foundation\Auth\User as Authenticatable;
use Illuminate\Notifications\Notifiable;
use Laravel\Sanctum\HasApiTokens;

class User extends Authenticatable
{
    use HasApiTokens, HasFactory, Notifiable;

    public function posts(): HasMany{
        return $this->hasMany(Post::class);
    }

    /**
     * The attributes that are mass assignable.
     *
     * @var array<int, string>
     */
    protected $fillable = [
        'name',
        'email',
        'password',
    ];

    /**
     * The attributes that should be hidden for serialization.
     *
     * @var array<int, string>
     */
    protected $hidden = [
        'password',
        'remember_token',
    ];

    /**
     * The attributes that should be cast.
     *
     * @var array<string, string>
     */
    protected $casts = [
        'email_verified_at' => 'datetime',
    ];
}

```

##### Post
```PHP
<?php

namespace App\Models;

use Illuminate\Database\Eloquent\Factories\HasFactory;
use Illuminate\Database\Eloquent\Model;

class Post extends Model
{
    use HasFactory;

    public function users(): BelongsTo {
        return $this->belongsTo(User::class);
    }

    public function comments(): HasMany {
        return $this->hasMany(Comment::class);
    }
}

```

##### Comment
```PHP
<?php

namespace App\Models;

use Illuminate\Database\Eloquent\Factories\HasFactory;
use Illuminate\Database\Eloquent\Model;

class Comment extends Model
{
    use HasFactory;

    public function posts(): BelongsTo {
        return $this->belongsTo(Post::class);
    }
}

```

### Migrations
##### User
##### Post
##### Comment

### Seeders
##### User
##### Post
##### Comment

### Factories
##### User
##### Post
##### Comment
