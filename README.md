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

# Erro Certificado Git

git config --global http.sslVerify false


# Comandos Git

![Comandos GIT](https://github.com/luthsanches/Help/blob/main/tech.juliana_278888544_3288556841372113_4377316700880951735_n.webp)
[Fonte](https://www.instagram.com/p/CcidY3WOmPH/?igshid=YmMyMTA2M2Y%3D)
[Instagram da fonte](https://www.instagram.com/tech.juliana/)


1️⃣ Configurar Informações Globais do Usuário
Defina seu nome e e-mail para que os commits sejam atribuídos corretamente:
𝘨𝘪𝘵 𝘤𝘰𝘯𝘧𝘪𝘨 --𝘨𝘭𝘰𝘣𝘢𝘭 𝘶𝘴𝘦𝘳.𝘯𝘢𝘮𝘦 "𝘚𝘦𝘶 𝘕𝘰𝘮𝘦" 
𝘨𝘪𝘵 𝘤𝘰𝘯𝘧𝘪𝘨 --𝘨𝘭𝘰𝘣𝘢𝘭 𝘶𝘴𝘦𝘳.𝘦𝘮𝘢𝘪𝘭 "𝘴𝘦𝘶𝘦𝘮𝘢𝘪𝘭@𝘦𝘹𝘢𝘮𝘱𝘭𝘦.𝘤𝘰𝘮"

2️⃣ Desfazer o último commit (mantendo as alterações)
Se cometeu um erro no último commit, você pode desfazer sem perder as modificações (isso é bem útil):
𝘨𝘪𝘵 𝘳𝘦𝘴𝘦𝘵 --𝘴𝘰𝘧𝘵 𝘏𝘌𝘈𝘋~𝟣

3️⃣ Modificar o último commit
Para adicionar mudanças ou alterar a mensagem do último commit:
𝘨𝘪𝘵 𝘢𝘥𝘥 .
𝘨𝘪𝘵 𝘤𝘰𝘮𝘮𝘪𝘵 --𝘢𝘮𝘦𝘯𝘥 -𝘮 "𝘕𝘰𝘷𝘢 𝘮𝘦𝘯𝘴𝘢𝘨𝘦𝘮 𝘥𝘰 𝘤𝘰𝘮𝘮𝘪𝘵"

4️⃣ Salvar alterações sem commit
Para alternar de branch sem fazer commit das alterações atuais:
𝘨𝘪𝘵 𝘴𝘵𝘢𝘴𝘩
Você pode recuperar posteriormente com:
𝘨𝘪𝘵 𝘴𝘵𝘢𝘴𝘩 𝘱𝘰𝘱

5️⃣ Visualizar histórico de commits graficamente
Para uma visualização compacta do histórico:
𝘨𝘪𝘵 𝘭𝘰𝘨 --𝘨𝘳𝘢𝘱𝘩 --𝘰𝘯𝘦𝘭𝘪𝘯𝘦 --𝘢𝘭𝘭

6️⃣ Alterar o autor do último commit
Se precisar corrigir o autor do commit:
𝘨𝘪𝘵 𝘤𝘰𝘮𝘮𝘪𝘵 --𝘢𝘮𝘦𝘯𝘥 --𝘢𝘶𝘵𝘩𝘰𝘳="𝘕𝘰𝘷𝘰 𝘈𝘶𝘵𝘰𝘳 <𝘯𝘰𝘷𝘰𝘦𝘮𝘢𝘪𝘭@𝘦𝘹𝘢𝘮𝘱𝘭𝘦.𝘤𝘰𝘮>"

7️⃣ Verificar diferenças nas alterações preparadas
Para ver o que está preparado para ser commitado:
𝘨𝘪𝘵 𝘥𝘪𝘧𝘧 --𝘴𝘵𝘢𝘨𝘦𝘥

8️⃣ Encontrar um bug com bisect
Para identificar o commit que introduziu um bug:
𝘨𝘪𝘵 𝘣𝘪𝘴𝘦𝘤𝘵 𝘴𝘵𝘢𝘳𝘵
𝘨𝘪𝘵 𝘣𝘪𝘴𝘦𝘤𝘵 𝘣𝘢𝘥      # 𝘊𝘰𝘮𝘮𝘪𝘵 𝘢𝘵𝘶𝘢𝘭 𝘤𝘰𝘮 𝘣𝘶𝘨
𝘨𝘪𝘵 𝘣𝘪𝘴𝘦𝘤𝘵 𝘨𝘰𝘰𝘥 <𝘩𝘢𝘴𝘩>  # 𝘊𝘰𝘮𝘮𝘪𝘵 𝘤𝘰𝘯𝘩𝘦𝘤𝘪𝘥𝘰 𝘴𝘦𝘮 𝘣𝘶𝘨

9️⃣ Listar todas as branches (locais e remotas)
Para visualizar todas as branches disponíveis:
𝘨𝘪𝘵 𝘣𝘳𝘢𝘯𝘤𝘩 -𝘢

🔟 Excluir uma branch local
Para remover uma branch que não é mais necessária:
𝘨𝘪𝘵 𝘣𝘳𝘢𝘯𝘤𝘩 -𝘥 𝘯𝘰𝘮𝘦-𝘥𝘢-𝘣𝘳𝘢𝘯𝘤𝘩
[Fonte](https://www.linkedin.com/feed/update/urn:li:activity:7288714464411967488/)
