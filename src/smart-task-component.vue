<script lang="ts">
import { defineComponent } from "vue";


export default /*#__PURE__*/ defineComponent({
  name: "SmartTaskComponent", // vue component name
  props: ['componentState', 'componentStatus'],
  data() {
    return { model: {} };
  },
  computed: {},
  methods: {
    async submitForm() {
      this.$emit("execute-smart-task", this.model);
    },
  },
  created() {
    if (this.componentState) {
      this.model = this.componentState;
    }
  },
  setup() {},
});
</script>


<template>
  <form>
    <div class="d-flex flex-row bd-highlight mb-3">
      <div class="w-100">
            <div
      class="
        notice
        d-flex
        bg-light-warning
        rounded
        border-warning border border-dashed
        mb-5
        p-3
      "
    >
      <span class="svg-icon svg-icon-2tx svg-icon-warning me-4"
        ><svg
          fill="none"
          viewBox="0 0 24 24"
          height="24"
          width="24"
          xmlns="http://www.w3.org/2000/svg"
        >
          <rect
            xmlns="http://www.w3.org/2000/svg"
            opacity="0.3"
            x="2"
            y="2"
            width="20"
            height="20"
            rx="10"
            fill="black"
          ></rect>
          <rect
            xmlns="http://www.w3.org/2000/svg"
            x="11"
            y="14"
            width="7"
            height="2"
            rx="1"
            transform="rotate(-90 11 14)"
            fill="black"
          ></rect>
          <rect
            xmlns="http://www.w3.org/2000/svg"
            x="11"
            y="17"
            width="2"
            height="2"
            rx="1"
            transform="rotate(-90 11 17)"
            fill="black"
          ></rect></svg
      ></span>
      <div class="d-flex flex-stack flex-grow-1">
        <div class="fw-bold">
          <div class="fs-6 text-gray-600">
            Complete the form below to schedule zoom meeting, once scheduled a
            invite will be sent to each of the participants, with a link to join
            the meeting.
          </div>
        </div>
      </div>
    </div>
         <div class="mb-3">
          <label class="form-label">Meeting Title</label>
          <input
            type="text"
            placeholder="New Meeting Request"
            class="form-control"
          />
          <div class="form-text">
            Specify a meeting title used as subject line when emailing participants.
          </div>
        </div>
         <div class="mb-3">
          <label class="form-label">Meeting Short Agenda</label>
          <textarea
            type="text"
            placeholder="Some short description for the meeting"
            class="form-control"
          ></textarea>
          <div class="form-text">
            Specify a short agenda of the meeting included in the body of the meeting invite.
          </div>
        </div>
        <div class="mb-3">
          <label class="form-label">Invite Participants</label>
          <input
            type="email"
            multiple
            placeholder="someone@test.com"
            class="form-control"
          />
          <div class="form-text">
            Specify comma seperated list of participants.
          </div>
        </div>
        <div class="row">
          <div class="col">
            <div class="mb-3">
              <label class="form-label">Meeting Start Date</label>
              <input type="datetime-local" class="form-control" />
              <div class="form-text">
                Specify the start date and time for the meeting. >/.
              </div>
            </div>
          </div>
          <div class="col">
            <div class="mb-3">
              <label class="form-label">Meeting Duration</label>
              <select class="form-control">
                <option value="15">15 minutes</option>
                <option value="30">30 minutes</option>
                <option value="45">45 minutes</option>
                <option value="60">1 Hour</option>
                <option value="90">1 Hour 30 Minutes</option>
              </select>
              <div class="form-text">
                Specify the meeting duration and click schedule meeting to
                schedule the meeting.
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <button type="submit" class="float-end btn btn-success">
      Schedule meeting
    </button>
  </form>
</template>

