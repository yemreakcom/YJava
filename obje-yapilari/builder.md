# 🏗️ Builder

## 🧱 Temel Kullanım

### ⭐ Kullanım Örneği

```java
NewsAPIOptions options = NewsAPIOptions.Builder()
    .setCountry("turkey")
    .setCategory("sports")
    .build();
```

### 👨‍💻 Kod Örneği

```java
public class NewsAPIOptions {

    private String country;
    private String category;
    private String sources;
    private String query;

    private int pageSize;
    private int page;

    private NewsAPIOptions(Builder builder) {
        this.country = builder.country;
        this.category = builder.category;
        this.sources = builder.sources;
        this.query = builder.query;
        this.pageSize = builder.pageSize;
        this.page = builder.page;
    }
    
    public static Builder Builder() {
        return new Builder();
    }
    
    public static final class Builder {

        String country = "tr";
        String category;
        String sources;
        String query;

        int pageSize = -1;
        int page = -1;

        public Builder setCountry(String country) {
            this.country = country;
            return this;
        }

        public Builder setCategory(String category) {
            this.category = category;
            return this;
        }

        public Builder setSources(String sources) {
            this.sources = sources;
            return this;
        }

        public Builder setQuery(String query) {
            this.query = query;
            return this;
        }

        public Builder setPageSize(int pageSize) {
            this.pageSize = pageSize;
            return this;
        }

        public Builder setPage(int page) {
            this.page = page;
            return this;
        }

        public NewsAPIOptions build() {
            return new NewsAPIOptions(this);
        }
    }
}
```

## 🌟 Enum ile Tanımlama

### ⭐ Kullanım Örneği

```java
NewsAPIOptions options = NewsAPIOptions.Builder()
    .setCountry(NewsAPIOptions.Country.US)
    .setCategory(NewsAPIOptions.Category.BUSINESS)
    .build();
```

### 👨‍💻 Kod Değişikliği

## 

```java
public class NewsAPIOptions {

    ...

    String category;
    String country;
    
    ...

    public enum Category {
    
            BUSINESS, ENTERTAINMENT, GENERAL, HEALTH, SCIENCE, SPORTS, TECHNOLOGY;
    
            public String getValue() {
                return this.name().toLowerCase();
            }
        }
    
    public enum Country {
    
        AE, AR, AT, AU, BE, BG, BR, CA, CH, CN, CO, CU, CZ, DE, EG, FR,
        GB, GR, HK, HU, ID, IE, IL, IN, IT, JP, KR, LT, LV, MA, MX, MY,
        NG, NL, NO, NZ, PH, PL, PT, RO, RS, RU, SA, SE, SG, SI, SK, TH,
        TR, TW, UA, US, VE, ZA;
    
        public String getValue() {
            return this.name().toLowerCase();
        }
    }
    
     public static final class Builder {
         ...
         
         String category;
         String country;

         ...
         
         public Builder setCategory(Category category) {
            this.category = category.getValue();
            return this;
        }
        
        public Builder setCountry(Country country) {
            this.country = country.getValue();
            return this;
        }
        
        ...
     }

}
```

## 🔗 Faydalı Kaynaklar

* [🐥 Named Parameter idiom in Java](https://stackoverflow.com/a/1988035/9770490)

