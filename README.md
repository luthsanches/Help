# Help

# IntelliJ Debug Json Result

new com.fasterxml.jackson.databind.ObjectMapper()
	.registerModule(new com.fasterxml.jackson.datatype.jsr310.JavaTimeModule())
	.disable(com.fasterxml.jackson.databind.SerializationFeature.WRITE_DATES_AS_TIMESTAMPS)
    .setSerializationInclusion(com.fasterxml.jackson.annotation.JsonInclude.Include.NON_NULL)
    .writerWithDefaultPrettyPrinter()
    .writeValueAsString( myObject )
