# Docker Perforce Images

Perforce docker images inspired by:
- Amit's [docker images](https://github.com/ambakshi/docker-perforce)
- Tilander's [p4 images](https://github.com/jtilander/docker-p4)
- Morita's [git-connector image](https://github.com/mmorita44/helix-git-connector)

The base images have all been switched to [baseimage docker](https://github.com/phusion/baseimage-docker) for proper zombie process handling and cron usage.

These images are also available on [docker hub](https://hub.docker.com/r/jtilander/)


## Usage

All operations on the images and repositories are encapsulated in the top level Makefile, which internally uses docker compose.

To install and run the full stack on your local computer, type:

    $ make [iterate]

To just build the images, simply type:

    $ make build


The docker compose file also uses external environment variables to configure itself, e.g. connecting to an LDAP server, so be sure to modify them if you need to.



## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D


## Credits

- Jim Tilander (jim@tilander.org)
- Amit Bakshi (ambakshi@gmail.com)

## License

- [Apache License 2.0](http://www.apache.org/licenses/LICENSE-2.0)


## References

  * https://github.com/phusion/baseimage-docker

