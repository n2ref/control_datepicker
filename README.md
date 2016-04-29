# Control datepicker


```html
<div class="ctrl-dpr">
  <div class="ctrl-dpr-controls">
      <input type="hidden" class="ctrl-dpr-from-value"
             name="period[date_from]" value=""/>
      <input type="hidden" class="ctrl-dpr-to-value"
             name="period[date_to]" value=""/>

      <input class="ctrl-dpr-from-day first input" min="1" max="31" autocomplete="off"
             placeholder="дд" type="number"/>
      <input class="ctrl-dpr-from-month middle input" min="1" max="12" autocomplete="off"
             placeholder="мм" type="number"/>
      <input class="ctrl-dpr-from-year middle input" max="9999" autocomplete="off"
             placeholder="гггг" type="number"/>

      <span class="ctrl-add-on"> - </span>

      <input class="ctrl-dpr-to-day middle input" min="1" max="31" autocomplete="off"
             placeholder="дд" type="number"/>
      <input class="ctrl-dpr-to-month middle input" min="1" max="12" autocomplete="off"
             placeholder="мм" type="number"/>
      <input class="ctrl-dpr-to-year middle input" max="9999" autocomplete="off"
             placeholder="гггг" type="number"/>

      <span class="ctrl-dpr-clear middle">
          <img src="/html/img/clear.png" alt="Очистить" title="Очистить">
      </span>
      <span class="ctrl-dpr-trigger last">
          <img src="/html/img/calendar.png" alt="..." title="...">
      </span>
  </div>
  <div class="clearfix"></div>
  <div class="ctrl-dpr-container" style="display: none"></div>
</div>


<script>
    $(document).ready(function(){
        $('.ctrl-dpr').each(function() {
            control_datepicker_range.create(this);
        });
        
        control_datepicker_range.setCallbackChange(function(date_from, date_to, wrapper) {
            // Функция выполняющаяся после изменения даты
        });
        
        // Функция выполняющаяся для раскраски календаря
        control_datepicker_range.setCallbackDayClass(function(date) {
            var year   = date.getFullYear();
            var month  = ('0' + (date.getMonth() + 1)).slice(-2);
            var day    = ('0' + (date.getDate())).slice(-2);
            var myDate = year + '-' + month + '-' + day;
            if (orders_edit.calendar[myDate] && orders_edit.calendar[myDate].type == 'weekend') {
                return 'dp-weekend';
            }
        });
    });
</script>
```
