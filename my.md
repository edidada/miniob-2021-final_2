# my
parse_stage.cpp
*error 变量没有使用

```cpp
  RC ret = parse(sql.c_str(), result);
  if (ret != RC::SUCCESS) {
    // set error information to event
    const char *error = result->sstr.errors != nullptr ? result->sstr.errors : "Unknown error";
    char response[256];
    snprintf(response, sizeof(response), "Failed to parse sql: %s\n", sql.c_str());
    sql_event->session_event()->set_response(response);
    query_destroy(result);
    return nullptr;
  }
```
