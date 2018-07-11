## <a name="using-the-username-or-userprincipalname-dax-function"></a>Использование функции DAX username() или userprincipalname()
Функции DAX *username()* и *userprincipalname()* в наборе данных обеспечивают определенные преимущества. Их можно использовать в выражениях в Power BI Desktop. При публикации модели она будет использоваться в службе Power BI.

В Power BI Desktop функция *username()* возвращает имя пользователя в формате *ДОМЕН\пользователь*, а функция *userprincipalname()* возвращает имя пользователя в формате <em>user@contoso.com</em>.

В службе Power BI *username()* и *userprincipalname()* возвращают имя участника-пользователя. Оно выглядит как адрес электронной почты.

