# five-example-of-vuejs


## Vuejs-of-Search



### Vuejs自定义过滤器filter

    // Define a custom filter called "searchFor".

    Vue.filter('searchFor', function (value, searchString) {

        // The first parameter to this function is the data that is to be filtered.
        // The second is the string we will be searching for.

        var result = [];

        if(!searchString){
            return value;
        }

        searchString = searchString.trim().toLowerCase();

        result = value.filter(function(item){
            if(item.title.toLowerCase().indexOf(searchString) !== -1){
                return item;
            }
        })

        // Return an array with the filtered data.

        return result;
    })
