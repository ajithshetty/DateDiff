def getListOfBetweenToDays(startDate:String)={
  import java.text.SimpleDateFormat
  import java.time.LocalDate
  import java.time.format.DateTimeFormatter
  import java.util.Calendar

  val load_format = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss")
  val formatter:DateTimeFormatter  = DateTimeFormatter.ofPattern("yyy-MM-dd HH:mm:ss");
  val from_date:LocalDate  = LocalDate.parse(startDate, formatter);

  val current_date = load_format.format(Calendar.getInstance().getTime())
  val to_date:LocalDate  = LocalDate.parse(current_date, formatter);


  /**
   * Generate an infinite stream of dates starting at `fromDate`.
   */
  def dates(fromDate: LocalDate): Stream[LocalDate] = {
    fromDate #:: dates(fromDate plusDays 1 )
  }

  dates(from_date.plusDays(1)).takeWhile(_.isBefore(to_date.plusDays(1))).toList
}
