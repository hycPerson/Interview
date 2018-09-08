0、购买域名服务器，跑通服务
1、搭建框架
2、角色设计
投资者、政府、管理者





实现Filter【javax.servlet.Filter】接口，实现Filter方法
添加 @Configuration 注解，将自定义Filter加入过滤链




/**
     * jsp视图解析器的bean
     * @return
     */
    @Bean
    public UrlBasedViewResolver setupViewResolver() {
        UrlBasedViewResolver resolver = new UrlBasedViewResolver();
        resolver.setPrefix("/WEB-INF/");
        resolver.setSuffix(".jsp");
        resolver.setViewClass(JstlView.class);
        return resolver;
    }

    /**
     * 配置数据源
     * @return
     */
    @Bean(name = "dataSource")
    public ComboPooledDataSource getDataSource() {
        try {

            ComboPooledDataSource dataSource = new ComboPooledDataSource();
            dataSource.setJdbcUrl("jdbc:mysql://localhost:3306/mfdb");
            dataSource.setDriverClass("com.mysql.jdbc.Driver");
            dataSource.setUser("root");
            dataSource.setPassword("zp1228");
            dataSource.setMaxPoolSize(75);
            return dataSource;
        } catch (Exception e) {
            return null;
        }
    }


String address, int roleCode
token里面三个信息：客户端地址，角色码，时间戳