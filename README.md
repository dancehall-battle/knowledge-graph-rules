# YARRRML rules to generate the knowledge graph

## Requirements
- [YARRRML Parser](https://github.com/rmlio/yarrrml-parser), if you want to convert the YARRRML rules to RML rules.
- [RMLMapper](https://github.com/RMLio/rmlmapper-java), if you want to execute the RML rules.
- [Data](https://github.com/dancehall-battle/knowledge-graph-data), referred to by the rules.

## Usage

1. Install dependencies via
   ```shell
   npm i
   ```
2. Generate RML rules via
   ```shell
   npm run rml
   ```
3. Put the CSV files in the folder `files`. 
4. Generate RDF via the RMLMapper
   ```shell
   java -Dfile.encoding="UTF-8" -jar rmlmapper-6.5.1-r371-all.jar -m rules.ttl -o data.ttl
   ```
5. You find the RDF in `data.ttl`.
6. Convert RDF file to HDT file via
   ```shell
   docker run -it --rm -v "$(pwd)":/data rfdhdt/hdt-cpp rdf2hdt -f turtle /data/data.ttl /data/data.hdt
   ```

## License

MIT &copy; Dancehall Battle
