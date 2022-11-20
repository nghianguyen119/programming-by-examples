# Automatic Static Optimization



|              | Non ASO (getServerSideProps)    | ASO                                                                                                  |
| ------------ | ------------------------------- | ---------------------------------------------------------------------------------------------------- |
| router.query | always available                | empty when pre-rendering, update after hydration                                                     |
| next build   | output an JS file for each page | output an HTML                                                                                       |
|              |                                 | All props will be sent to client, in script \_\_NEXT\_DATA\_\_\_, only send neccessary data to props |
