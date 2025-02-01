## Step 1. Model
  - Create the Model Folder and add class

```C#
namespace _0durgeshsingh.Models
{
    public class Person
    {
        public int Id { get; set; }
        public string Name { get; set; }
        public string PhoneNumber { get; set; }
    }
}
```
## Step 2. Create Application Context Class
  - Create a Folder Data and Add a Context Class 

```C#
using _0durgeshsingh.Models;
using Microsoft.EntityFrameworkCore;

namespace _0durgeshsingh.Data
{
    // Define the ApplicationDbContext class, which inherits from DbContext

    public class ApplicationDbContext : DbContext     
    {
        // Constructor that accepts DbContextOptions and passes it to the base DbContext class
        public ApplicationDbContext(DbContextOptions<ApplicationDbContext> options) : base(options) {

            // The constructor is used to configure the context with specific options (e.g., database settings)
        }

        // DbSet property for accessing and querying the 'Persons' table in the database
        // DbSet represents a collection of entities of type Person that can be queried or saved to the database
        public DbSet<Person> Persons { get; set; }
    }
}
```
