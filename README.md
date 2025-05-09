# Celestial-bodies-database


# Celestial Bodies Database

This project contains a PostgreSQL database schema and data dump for a database named `universe`. The database models celestial objects such as galaxies, stars, planets, moons, and comets, along with their relationships and attributes.

## Database Structure

The database consists of the following tables:

### 1. `galaxy`
- **Columns**:
  - `galaxy_id` (Primary Key): Unique identifier for each galaxy.
  - `name`: Name of the galaxy.
  - `description`: Description of the galaxy.
  - `distance_from_earth`: Distance from Earth in light-years.
  - `age_in_millions_of_years`: Age of the galaxy in millions of years.
  - `has_life`: Boolean indicating if the galaxy contains life.

### 2. `star`
- **Columns**:
  - `star_id` (Primary Key): Unique identifier for each star.
  - `name`: Name of the star.
  - `galaxy_id` (Foreign Key): References the `galaxy` table.
  - `type`: Type of the star (e.g., G-type, M-type).
  - `age_in_millions_of_years`: Age of the star in millions of years.
  - `has_planets`: Boolean indicating if the star has planets.

### 3. `planet`
- **Columns**:
  - `planet_id` (Primary Key): Unique identifier for each planet.
  - `name`: Name of the planet.
  - `star_id` (Foreign Key): References the `star` table.
  - `type`: Type of the planet (e.g., Terrestrial, Gas Giant).
  - `distance_from_star`: Distance from its star in astronomical units (AU).
  - `is_spherical`: Boolean indicating if the planet is spherical.

### 4. `moon`
- **Columns**:
  - `moon_id` (Primary Key): Unique identifier for each moon.
  - `name`: Name of the moon.
  - `planet_id` (Foreign Key): References the `planet` table.
  - `type`: Type of the moon (e.g., Rocky, Icy).
  - `has_life`: Boolean indicating if the moon contains life.

### 5. `comet`
- **Columns**:
  - `comet_id` (Primary Key): Unique identifier for each comet.
  - `name`: Name of the comet.
  - `description`: Description of the comet.
  - `period_years`: Orbital period in years.
  - `origin`: Origin of the comet (e.g., Oort Cloud, Kuiper Belt).

## Data

The database includes sample data for all tables, such as:
- Galaxies like the Milky Way and Andromeda.
- Stars like the Sun and Proxima Centauri.
- Planets like Earth and Jupiter.
- Moons like the Moon and Europa.
- Comets like Halley's Comet and Hale-Bopp.

## Constraints and Relationships

- Each table has a primary key for unique identification.
- Foreign key constraints enforce relationships between tables:
  - `star.galaxy_id` references `galaxy.galaxy_id`.
  - `planet.star_id` references `star.star_id`.
  - `moon.planet_id` references `planet.planet_id`.
- Unique constraints ensure no duplicate names for celestial objects.

