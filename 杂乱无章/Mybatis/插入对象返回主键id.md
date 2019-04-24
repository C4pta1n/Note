Mapper:

``

    @Insert("insert into account (username, password, tel, email) values (#{username}, #{password}, #{tel}, #{email})")
    @Options(useGeneratedKeys = true,keyProperty = "aid",keyColumn = "aid")     //加入该注解可以保持对象，查看对象插入主键id
    Integer addAccount(Account account);
    
    
``

Service:

``

    public Integer signup(Account account) {
        Integer aid = account.getAid();     //mapper给account对象返回了主键id，可以直接获取
        return accountMapper.addAccount(account);   //返回了操作成功的记录数
    }

``

