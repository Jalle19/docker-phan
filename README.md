# docker-phan

This is a docker container for the [phan](https://github.com/etsy/phan/) static analyser.

## Usage

Just start the container, mount your code somehow, then run `phan` however you want inside it. In contrast to all 
other containers for this tool this one doesn't try to insult your intelligence by limiting how you use the tool.

### GitLab CI example

These examples assume you have a `.phan/config.php` file in your project's root directory.

```yaml
phan:
  image: nordsoftware/phan
  script:
    - phan
```

### Jenkins Pipeline example

```
node {    
    stage('Run static analysis') {
        docker.image('nordsoftware/phan').inside {
            sh 'phan'
        }    
    }
}
```

## Versioning

Each version is tagged with the version of phan it ships.

### Credits

Credits to [mre/docker-php-phan](https://github.com/mre/docker-php-phan) for the installation instructions.
