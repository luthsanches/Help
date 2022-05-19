# Help

# IntelliJ Debug Json Result

new com.fasterxml.jackson.databind.ObjectMapper()
	.registerModule(new com.fasterxml.jackson.datatype.jsr310.JavaTimeModule())
	.disable(com.fasterxml.jackson.databind.SerializationFeature.WRITE_DATES_AS_TIMESTAMPS)
    .writerWithDefaultPrettyPrinter()
    .writeValueAsString( myObject )
    
# Configuração de bean para mapeamento de Json para RestTemplate (necessário adicionar em uma classe de configuração)

@Bean
public RestTemplate restTemplate(RestTemplateBuilder builder) {
        
        RestTemplate restTemplate = builder
                .setConnectTimeout(timeout)
                .build();
        
        MappingJackson2HttpMessageConverter mappingJackson2HttpMessageConverter =
                new MappingJackson2HttpMessageConverter();
        mappingJackson2HttpMessageConverter.setSupportedMediaTypes(
                Arrays.asList(MediaType.APPLICATION_JSON, MediaType.APPLICATION_OCTET_STREAM));
        
        restTemplate.getMessageConverters().add(mappingJackson2HttpMessageConverter);
        return restTemplate;
    }

