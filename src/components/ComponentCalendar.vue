<template>
  <div class="w-full h-full flex items-center justify-center">
    <Calendar
      v-model:checkIn="checkIn"
      v-model:checkOut="checkOut"
      :booked-dates="bookedDates"
      :period-dates="periodDates"
      :booking-dates="bookingDates"
      @renderNextMonth="renderNextMonth"
    />
  </div>
</template>

<script>
import { Calendar } from "vue-calendar-3";

export default {
  name: "ComponentCalendar",
  components: {
    Calendar,
  },
  data() {
    return {
      bookedDates: [
        "2021-07-01",
        "2021-07-02",
        "2021-07-03",
        "2021-07-23",
        "2021-07-24",
        "2021-07-25",
      ],
      countPaginate: 0,
      periodDates: [
        {
          startAt: "2021-07-01",
          endAt: "2021-08-31",
          minimumDuration: 4,
          periodType: "nightly",
        },
        {
          startAt: "2021-09-01",
          endAt: "2021-09-30",
          minimumDuration: 2,
          periodType: "weekly_by_saturday",
        },
        {
          startAt: "2021-10-01",
          endAt: "2021-10-30",
          minimumDuration: 4,
          periodType: "nightly",
        },
        {
          startAt: "2021-11-01",
          endAt: "2021-11-29",
          minimumDuration: 1,
          periodType: "weekly_by_sunday",
        },
      ],
      checkIn: null,
      checkOut: null,
      nextBookedDates: [
        "2021-12-01",
        "2021-12-02",
        "2021-12-03",
        "2021-12-04",
        "2021-12-05",
        "2021-12-06",
        "2021-11-14",
        "2021-11-15",
        "2021-11-16",
        "2021-11-17",
        "2021-11-18",
        "2021-11-19",
        "2021-11-20",
        "2021-11-21",
      ],
    };
  },
  methods: {
    renderNextMonth() {
      this.countPaginate++;
    },
  },
};
</script>

<style></style>
